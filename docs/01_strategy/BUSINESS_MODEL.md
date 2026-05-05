# BUSINESS MODEL — AmanaTrade

## Objectif de ce document
Décrire comment AmanaTrade crée, délivre et capture de la valeur.

---

## Modèle de revenus

> **Hypothèse principale (non encore validée terrain) :** Commission par transaction sécurisée, avec minimum forfaitaire.

| Source de revenus | Description | Hypothèse MVP | Statut |
|---|---|---|---|
| **Commission transaction (détail)** | % prélevé sur chaque transaction sécurisée entre vendeur et acheteur | **2,5 % à 3 %** du montant | Hypothèse — à valider terrain Phase 1 |
| **Minimum forfaitaire** | Frais plancher pour les petites transactions | **500 ₦ minimum** | Hypothèse — benchmark EscrowLock/Peppa |
| Abonnement vendeur (futur) | Forfait mensuel pour les vendeurs très actifs | Non chiffré | Hors scope MVP — à explorer Phase 3 |
| Commission grossiste (futur) | Taux réduit pour volumes importants (Kantin Kwari) | ~1,25 % | Hors scope MVP |
| Services premium (futur) | Visibilité, badge de confiance, analytics | Non chiffré | Hors scope MVP |

**Références benchmark :** EscrowLock et Peppa.io pratiquent 1,25 %–3,25 %. La fourchette 2,5–3 % est retenue comme hypothèse haute pour le segment détail Kano, justifiée par l'inclusion d'une garantie de résolution de litiges.

**Note sur le cadre islamique :** Les frais de service d'AmanaTrade doivent être présentés et structurés comme **Ujrah** (honoraires de service légitimes) et non comme Riba (intérêts), conformément aux principes de finance islamique en vigueur à Kano (Nord Nigeria). Voir Wakalah dans `docs/03_legal/ESCROW_LEGAL_OPTIONS.md`.

---

## Segments clients

### Vendeurs — côté offre

**Profil principal (early adopter MVP) :**
- Âge : 20–35 ans
- Lieu : Sabon Gari (Muhammad Abubakar Rimi Market), Kano
- Secteur : chaussures de sport importées, mode féminine premium (Abayas, Modest wear)
- Comportement : actif sur Instagram et WhatsApp, smartphone milieu de gamme, déjà utilisateur de services de livraison tiers
- **Douleur principale :** annulations de commandes à la livraison (Cash-on-Delivery) + méfiance des acheteurs hors Kano refusant de payer à l'avance
- Motivation : sécuriser des transactions sans risque de livraison à vide, attirer des acheteurs distants qui ne les connaissent pas

**Profil secondaire (extension Phase 2) :**
- Vendeurs plus âgés, segment textile, Kantin Kwari
- Grossistes cherchant à sécuriser des lots importants

### Acheteurs — côté demande

**Profil principal (early adopter MVP) :**
- Lieu : Kano et environs (dont universités — Bayero University)
- Comportement : achète des vêtements en ligne pour gagner du temps, suit les tendances sur TikTok, budget limité, aversion élevée au risque de fraude
- **Douleur principale :** a déjà été victime d'un produit non conforme ("What I ordered vs what I got") ou d'une arnaque WhatsApp
- Motivation : obtenir une garantie de remboursement simple en cas de non-conformité du produit

---

## Canaux de distribution

| Canal | Priorité | Description | Coût estimé |
|---|---|---|---|
| **Lien WhatsApp direct (deep link)** | Priorité 1 | Le vendeur partage un lien de transaction AmanaTrade directement dans sa conversation WhatsApp | Très faible |
| **WhatsApp Status du vendeur** | Priorité 1 | Lien de transaction ou badge "Vendeur vérifié AmanaTrade" intégré dans le Status | Très faible |
| **Recrutement via Startup Kano / Blue Sapphire Hub** | Priorité 1 (Phase 1) | Identification de vendeurs champions dans les hubs tech locaux | Faible |
| **Bouche-à-oreille entre vendeurs** | Priorité 2 | Un vendeur convaincu recommande à ses pairs | Nul |
| **Présence physique marché Sabon Gari** | Priorité 2 (modèle concierge) | Accompagnement terrain des premières transactions — Phase 1 uniquement | Moyen (déplacement) |
| Associations de commerçants (unions) | Phase 2 | Accès groupé aux vendeurs via structures existantes | Moyen |
| Publicité digitale | Phase 3 | Meta Ads, TikTok — hors scope MVP | Variable |

---

## Structure de coûts (estimation initiale)

> Détail dans `docs/02_finance/STARTUP_BUDGET.md`

**Grandes catégories :**
- Développement PWA (Phase 2) : 3 000–5 000 € estimés
- Conseil juridique nigérian : 500–2 000 € estimés (selon cabinet)
- Infrastructure cloud (hébergement, APIs, SMS) : < 200 €/mois en phase pilote
- Coûts PSP par transaction : ~1,5 % (intégrés dans la marge de la commission AmanaTrade)
- Déplacements terrain Kano (Phase 1) : 500–1 500 €
- Marketing Phase 1 : < 500 € (focus acquisition manuelle)

---

## Partenaires clés pressentis

| Partenaire | Rôle | Statut |
|---|---|---|
| **Monnify** (priorité 1) | PSP — DVA + Webhook + Disbursement | À contacter — sandbox à tester |
| **Squad** (priorité 1) | PSP alternatif | À contacter — sandbox à tester |
| **Startup Kano** | Hub recrutement vendeurs champions | À contacter |
| **Blue Sapphire Hub** | Hub recrutement vendeurs champions | À contacter |
| **Peng Logistics** | Livraison + vérification physique à la livraison | À contacter |
| **Sendvoy** | Livraison B2B last-mile Kano | À contacter |
| Avocat nigérian fintech/CBN | Validation légale architecture paiement | À identifier — priorité absolue |

---

## Proposition de valeur

### Pour le vendeur
> *"Reçois l'argent de tes clients en toute sécurité avant d'expédier, sans risque d'annulation à la livraison."*

- Élimination des annulations Cash-on-Delivery
- Confiance augmentée des acheteurs distants (hors Kano)
- Badge "Vendeur AmanaTrade" = signal de crédibilité sur WhatsApp
- Résolution de litiges si conflit

### Pour l'acheteur
> *"Paie en toute confiance : ton argent est protégé jusqu'à ce que tu reçoives exactement ce que tu as commandé."*

- Garantie de remboursement si produit non conforme ou non livré
- Pas besoin de faire confiance au vendeur a priori
- Processus simple via lien WhatsApp, pas d'application à télécharger

---

## Hypothèses clés à valider terrain (Phase 1)

| # | Hypothèse | Méthode de validation |
|---|---|---|
| **H-BM-01** | Les vendeurs WhatsApp de Sabon Gari sont prêts à payer 2,5–3 % de commission pour sécuriser leurs transactions | Interviews Phase 1 + test pilote |
| **H-BM-02** | Le ticket moyen réel des transactions WhatsApp chaussures à Kano est ≥ ₦15 000 (seuil minimal de rentabilité) | Interviews vendeurs Phase 1 |
| **H-BM-03** | Les acheteurs sont prêts à utiliser un lien de paiement tiers s'il est présenté comme "Amana" | Test UX Phase 1 |
| **H-BM-04** | La commission par transaction est préférable à un abonnement mensuel pour les vendeurs MVP | Interviews Phase 1 |
| **H-BM-05** | Les frais structurés en Ujrah ne créent pas de résistance religieuse significative dans la cible | Interviews Phase 1 |
| **H-BM-06** | L'interface en haoussa est un facteur d'adoption déterminant et pas seulement un "nice to have" | Interviews Phase 1 |
| **H-BM-07** | Le modèle concierge (accompagnement physique) est nécessaire pour les 4 premières semaines de pilote | Phase 1 opérationnelle |

---

## Décisions en attente

| Décision | Bloquée par | Voir |
|---|---|---|
| Taux de commission exact (2,5 % vs 3 %) | Validation terrain + avis fondateur | DECISION_LOG.md D-P1 |
| Architecture de rétention des fonds (Option B vs Option E) | Validation légale avocat | ESCROW_LEGAL_OPTIONS.md |
| Modèle d'abonnement ou non | Interviews terrain Phase 1 | RESEARCH_BACKLOG.md R5 |

---

*Responsable : Business & Finance Agent*
*Mis à jour : 2026-05-05 — après analyse recherche marché Kano*
*Sources : docs/08_research/market/reviewed/2026-05-05_kano-whatsapp-commerce-review.md*
