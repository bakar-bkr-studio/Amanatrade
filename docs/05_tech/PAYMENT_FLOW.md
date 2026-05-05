# PAYMENT FLOW — AmanaTrade

## Objectif de ce document
Documenter le flux de paiement et de séquestre étape par étape, en intégrant les contraintes légales, techniques et utilisateur.

*Mis à jour le 2026-05-05 sur la base de la revue de recherche : `docs/08_research/payments/reviewed/2026-05-05_nigeria-payment-providers-review.md`*

---

## Principes d'architecture (issus de la recherche)

1. **AmanaTrade ne détient jamais de fonds directement.** Les fonds transitent et sont retenus dans l'infrastructure du PSP licencié (Monnify, Squad ou équivalent). Cela est non négociable au regard des réglementations CBN (risque RL-01).
2. **Le Compte Virtuel Dédié (DVA / Reserved Account NUBAN) est le mécanisme central.** Chaque transaction génère ou utilise un NUBAN associé. Le virement de l'acheteur vers ce NUBAN déclenche automatiquement la confirmation via Webhook — pas de vérification manuelle.
3. **La commission AmanaTrade est prélevée automatiquement** via le Split Payment API au moment du décaissement, pas au moment de l'encaissement.
4. **La libération des fonds au vendeur est déclenchée par le backend AmanaTrade** via l'API de Disbursement (Single Transfer), uniquement après confirmation de réception par l'acheteur ou expiration du délai de litige.

---

## Flux principal — Happy Path

```
[Acheteur]                      [PWA AmanaTrade]               [PSP Licencié]         [Vendeur]
    |                                   |                             |                     |
    |-- Accepte l'offre WhatsApp -----→ |                             |                     |
    |                                   |-- Crée la transaction       |                     |
    |                                   |-- Génère/attribue DVA ----→ |                     |
    |  ← Reçoit NUBAN + montant ------- |                             |                     |
    |                                   |                             |                     |
    |-- Transfère le montant ----------→|→ (via réseau NIBSS)→→→→→→→→|                     |
    |                                   |  ← Webhook charge.success - |                     |
    |                                   |   (fonds retenus dans PSP)  |                     |
    |  ← Statut : "Paiement confirmé"   |                             |                     |
    |                                   |-- Notifie : "Tu peux livrer" →→→→→→→→→→→→→→→→→→→ |
    |                                   |                             |                     |
    |                      [Vendeur expédie la marchandise]           |                     |
    |                                   |                             |   ← Déclare expédition
    |  ← Notifié : "En cours de livraison"                           |                     |
    |                                   |                             |                     |
    |-- Confirme réception -------------→|                            |                     |
    |                                   |-- Disbursement API -------→ |                     |
    |                                   |   (montant - commission)    |→ Virement NUBAN →→→ |
    |  ← Statut : "Transaction clôturée"|                             |                     |
    |                                   |                             |  ← Reçoit paiement  |
```

### Détail des étapes techniques

| Étape | Action | Mécanisme technique | PSP concerné |
|---|---|---|---|
| 1 | Création de la transaction | Backend AmanaTrade crée un enregistrement en DB | — |
| 2 | Génération du DVA | Appel API : `POST /reserved-account` (Monnify) ou `POST /virtual-account` (Squad) | Monnify / Squad |
| 3 | Paiement acheteur | Virement bancaire / USSD / OPay → NUBAN | NIBSS |
| 4 | Confirmation automatique | Webhook `charge.success` ou `payment.notification` → backend | Monnify / Paystack |
| 5 | Notification vendeur | Push notification PWA + SMS/WhatsApp | Backend |
| 6 | Déclaration expédition | Vendeur clique "J'ai expédié" dans la PWA | Backend |
| 7 | Confirmation réception | Acheteur clique "J'ai reçu" dans la PWA | Backend |
| 8 | Libération des fonds | Appel API : `POST /single-transfer` (Monnify) ou `/disburse` (Squad) | Monnify / Squad |
| 9 | Prélèvement commission | Inclus dans le Disbursement (Split défini à la configuration du vendeur) | Monnify / Flutterwave |

---

## Flux alternatif — Litige ouvert par l'acheteur

```
[Acheteur]                      [PWA AmanaTrade]               [PSP]              [Vendeur]
    |                                   |                         |                    |
    |-- Ouvre un litige ---------------→|                         |                    |
    |   (dans les 48h post-livraison déclarée)                    |                    |
    |                                   |-- Notifie le vendeur -→ |→→→→→→→→→→→→→→→→→→ |
    |                                   |                         |  ← Réponse vendeur |
    |                                   |                         |                    |
    |            [Résolution AmanaTrade dans 72h]                 |                    |
    |                                   |                         |                    |
    | Si remboursement décidé :         |                         |                    |
    |                                   |-- Refund API ----------→|                    |
    |  ← Remboursement vers acheteur    |                         |                    |
    |                                   |                         |                    |
    | Si paiement vendeur décidé :      |                         |                    |
    |                                   |-- Disbursement API ----→|→→→→→→→→→→→→→→→→→→ |
```

*Voir `docs/06_marketing_operations/DISPUTE_RESOLUTION_POLICY.md` pour les critères de décision.*

---

## Flux alternatif — Acheteur ne confirme pas dans les délais

```
Acheteur ne confirme pas la réception dans les 48h suivant la livraison déclarée :
→ Système envoie une relance automatique (push/SMS)
→ Si toujours pas de confirmation après 72h :
   → Libération automatique des fonds au vendeur (Disbursement API)
   → Acheteur notifié que le délai est expiré
```

*Délais exacts à définir et valider avec `DISPUTE_RESOLUTION_POLICY.md`. Ces valeurs (48h, 72h) sont des hypothèses initiales.*

---

## Flux alternatif — Vendeur ne déclare pas l'expédition

```
Vendeur n'a pas déclaré l'expédition dans les X jours suivant la confirmation de paiement :
→ Système envoie une relance automatique
→ Si toujours pas de réponse après Y jours :
   → Remboursement automatique de l'acheteur (Refund API)
   → Vendeur notifié
```

*Délais à définir. Hypothèse de départ : X = 3 jours, Y = 5 jours.*

---

## Flux alternatif — Échec ou timeout du paiement

```
Acheteur initie le virement mais les fonds n'arrivent pas (timeout réseau NIBSS) :
→ DVA reste actif (si DVA permanent / Reserved Account)
→ Statut : "En attente de paiement"
→ Relance automatique après X heures
→ Si aucun paiement après 24h : transaction annulée, DVA désaffecté
```

---

## Canaux de paiement supportés (MVP)

| Canal | Priorité MVP | Mécanisme | Notes |
|---|---|---|---|
| Virement bancaire (Bank Transfer) | ✅ Priorité 1 | Via DVA NUBAN + NIBSS | Canal dominant à Kano |
| USSD | ✅ Priorité 1 | Compatible avec les virements bancaires USSD standard | Pas d'internet requis |
| OPay / PalmPay | ✅ Priorité 2 | Via Korapay (API unifiée) ou DVA Monnify | Très utilisés à Kano |
| Carte bancaire (Mastercard/Visa/Verve) | ❌ Hors MVP | — | Friction trop élevée, adoption faible dans la cible |

---

## PSP pressentis (à confirmer par test sandbox)

| PSP | Avantage principal | Inconvénient | Priorité test |
|---|---|---|---|
| **Monnify** | Settlement biquotidien, DVA permanents, Split API native | Moins connu que Paystack | ⭐ Priorité 1 |
| **Squad (HabariPay)** | DVA le moins cher (0.25 % plafonné à ₦1 000), GTCO infrastructure | Moins mature en API | ⭐ Priorité 1 |
| **Paystack** | Meilleure DX, confirmation < 8s (Titan), références solides | DVA à 1 % (plafonné à ₦300) | ⭐ Priorité 2 |
| **Korapay** | Intègre OPay/PalmPay, refund console avancée | Moins connu pour Split escrow | Priorité 3 |
| **Flutterwave** | Split API mature, subaccounts marketplace | Settlement T+1 à T+3 variable | Priorité 3 |

---

## Contraintes KYC sur les montants de transaction

> **⚠️ Alerte issue de la recherche légale (`docs/08_research/legal/reviewed/2026-05-05_nigeria-escrow-regulation-review.md`)**

La réglementation CBN KYC impose des plafonds stricts par niveau d'identification :

| Niveau KYC | Plafond par dépôt | Solde cumulé max | Exigences |
|---|---|---|---|
| **Tier 1** (BVN ou NIN seul) | **₦20 000** (~12–15 €) | ₦200 000 | BVN/NIN + téléphone + vérification physique adresse (juin 2024) |
| **Tier 2** (pièce d'identité officielle) | **₦50 000** (~30–35 €) | ₦500 000 | Passeport / permis / carte d'électeur vérifiés |
| **Tier 3** (diligence raisonnable complète) | Sans limite | Sans limite | Vérification physique, origine des fonds |

### Implications pour le flux de paiement MVP

- **Si ticket moyen ≤ ₦20 000** → Tier 1 suffisant. Onboarding simplifié (BVN/NIN uniquement).
- **Si ticket moyen > ₦20 000** → Tier 2 requis. Friction supplémentaire (pièce d'identité).
- **Ticket moyen réel à Kano = inconnu** → À valider lors des interviews terrain Phase 1 (voir `HUMAN_ACTIONS.md`).

### Décision de conception (hypothèse de travail)
Le MVP est conçu par défaut pour des transactions ≤ ₦20 000 (Tier 1). Un flux de montée en Tier 2 est prévu mais non prioritaire pour le lancement. Cette hypothèse sera révisée après les interviews terrain.

> **Note :** La mise à jour CBN de juin 2024 exige une vérification physique d'adresse même pour le Tier 1. Ce point est un risque opérationnel non résolu — voir `LEGAL_RISK_REGISTER.md` R011 et `AGENT_QUESTIONS.md`.

---

## Questions ouvertes (transférées vers AGENT_QUESTIONS.md)

- La structure Split+Disbursement est-elle confirmée légalement conforme CBN sans licence propre ? (⚠️ À valider par avocat)
- Quel délai de confirmation automatique avant libération des fonds (48h ? 72h ?)
- Comment prouver la livraison dans un contexte sans tracking physique ?
- OPay/PalmPay sont-ils compatibles en entrée avec les DVA NUBAN de Monnify/Squad ?
- Quelles sont les conditions contractuelles concrètes de Monnify et Squad pour l'onboarding d'une nouvelle startup ?

---

## Hypothèses actées dans ce document

> Ces choix sont des hypothèses de travail, pas des décisions définitives. Ils guident la conception technique en attendant validation.

- H1 : Architecture Hold & Release via PSP licencié = conforme CBN (⚠️ À valider avocat)
- H2 : Monnify ou Squad = PSP principal du MVP
- H3 : DVA permanents (Reserved Accounts) = meilleure UX que DVA dynamiques avec expiration
- H4 : Délai de confirmation acheteur = 48h, délai de litige = 72h (à valider terrain + légal)

---

*Responsable : Tech Architecture Agent + Legal & Compliance Agent*
*Source principale : `docs/08_research/payments/reviewed/2026-05-05_nigeria-payment-providers-review.md`*
*Dépendances : ESCROW_LEGAL_OPTIONS.md, TECH_ARCHITECTURE.md, DISPUTE_RESOLUTION_POLICY.md*
*Mis à jour le : 2026-05-05*
