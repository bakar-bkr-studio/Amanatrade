# FIELD TEST PLAN — AmanaTrade

## Objectif de ce document
Planifier le test terrain du MVP à Kano : qui recruter, comment tester, et comment mesurer le succès.

---

## Hypothèses à valider lors du test terrain

| # | Hypothèse | Méthode de validation |
|---|---|---|
| HF-01 | Les vendeurs WhatsApp de Sabon Gari (chaussures + mode premium) sont prêts à payer 2,5–3 % de commission | Interviews + test pilote |
| HF-02 | Les acheteurs font confiance à un lien AmanaTrade envoyé par un vendeur qu'ils ne connaissent pas | Test UX terrain |
| HF-03 | Le flux UX est compréhensible sans formation, en haoussa, sur Android entrée de gamme | Test utilisabilité terrain |
| HF-04 | Le modèle concierge (accompagnement physique des premières transactions) est nécessaire pour l'adoption initiale | Observation terrain |
| HF-05 | Les vendeurs acceptent d'attendre 24h après livraison pour recevoir leurs fonds | Interviews + observation |
| HF-06 | L'interface haoussa réduit significativement la résistance à l'adoption | Observation + questionnaire |
| HF-07 | Le ticket moyen réel des transactions WhatsApp chaussures à Kano est ≥ ₦20 000 | Données transactionnelles |
| HF-08 | Peng Logistics / Sendvoy peuvent servir de partenaire de livraison opérationnel | Test logistique terrain |
| HF-09 | Le terme "AmanaTrade" / le concept d'Amana crée un avantage de crédibilité perceptible | Interviews acheteurs et vendeurs |

---

## Plan de recrutement des participants

### Vendeurs pilotes — Cible : 10 à 30

**Critères de sélection :**
- Actif sur WhatsApp (Status utilisé au moins 3 fois par semaine)
- Vend des chaussures de sport ou de la mode féminine premium (Abayas, Modest wear)
- Basé au marché Sabon Gari, Kano
- Âge : 20–35 ans de préférence (meilleure familiarité avec le numérique)
- A déjà eu au moins un problème lié au paiement (annulation COD, retard, arnaque)

**Méthode de recrutement :**
1. Contact initial via **Startup Kano** et **Blue Sapphire Hub** (identification de vendeurs ayant déjà une présence numérique)
2. Présence physique au marché Sabon Gari avec un relais local de confiance
3. Recommandation par le premier vendeur converti (effet de réseau)
4. Compensation proposée : pas de compensation financière directe en Phase 1 — le service lui-même est la proposition de valeur (zéro commission pendant les 10 premières transactions pilote, à confirmer par le fondateur)

**Questions à poser en entretien de recrutement :**
- *"Combien de clients vous demandent 'puis-je payer à la livraison ?' et comment gérez-vous le risque ?"*
- *"Quelle est la principale raison pour laquelle vos transactions échouent après une discussion WhatsApp ?"*
- *"Si un service bloquait l'argent du client avant que vous n'envoyiez le colis, seriez-vous prêt à attendre 24h après la livraison pour recevoir vos fonds ?"*
- *"Quels termes en haoussa utilisez-vous pour rassurer vos clients sur votre honnêteté ?"*
- *"À combien estimez-vous votre ticket moyen de vente chaussures sur WhatsApp ?"*

### Acheteurs pilotes — Cible : 20 à 50

**Critères de sélection :**
- A déjà acheté au moins une fois via WhatsApp (vêtements ou chaussures)
- Basé à Kano ou environs immédiats
- A connu au moins une expérience négative (produit non conforme, arnaque, ou forte hésitation à payer à l'avance)

**Méthode de recrutement :**
- Recrutés principalement via les vendeurs pilotes (leurs propres clients)
- Bouche-à-oreille dans les universités de Kano (Bayero University)
- Pas de compensation financière directe — la garantie de remboursement est la proposition de valeur

**Questions à poser en entretien acheteur :**
- *"Quel est le montant maximum que vous seriez prêt à payer par virement à un vendeur que vous n'avez jamais rencontré physiquement ?"*
- *"Qu'est-ce qui vous rassurerait le plus : une photo de la boutique physique ou une garantie de remboursement par une application tierce ?"*
- *"Si le produit ne correspond pas, préférez-vous un remboursement total ou une remise sur le prochain achat ?"*
- *"Seriez-vous à l'aise avec le fait de devoir confirmer la réception dans une application dans les 24h ?"*

---

## Protocole de test — Modèle concierge Phase 1

> **Principe du modèle concierge :** Pendant les premières semaines, un membre de l'équipe AmanaTrade (ou le relais local) accompagne physiquement les premières transactions. Objectif : résoudre les bugs en temps réel, rassurer les parties, et collecter des données comportementales impossibles à obtenir à distance.

### Semaine 1–2 — Onboarding des vendeurs pilotes
- Rencontrer chaque vendeur pilote en personne à Sabon Gari
- Guider l'inscription (téléphone, BVN, profil)
- Créer la première transaction ensemble
- Expliquer le flux complet (lien → paiement acheteur → expédition → confirmation → réception des fonds)
- Documenter chaque friction observée (photo, note, enregistrement audio si accord)

**Livrables semaine 1–2 :**
- Fiche de profil pour chaque vendeur inscrit
- Liste des frictions d'onboarding documentées
- Premier rapport terrain transmis au fondateur

### Semaines 3–4 — Premières transactions accompagnées
- Accompagner (à distance ou en présence) les 3 premières transactions de chaque vendeur pilote
- Pour chaque transaction : vérifier que le lien fonctionne, que le paiement est bien reçu, que le webhook se déclenche
- Gérer manuellement tout litige ou bug technique en moins de 2h
- Appeler l'acheteur pour son premier retour d'expérience après réception

**Livrables semaines 3–4 :**
- Log détaillé de chaque transaction (statut, durée, problèmes, résolution)
- 10 mini-interviews acheteurs (post-transaction)
- Rapport de friction UX pour le développeur

### Semaines 5–6 — Transactions autonomes
- Les vendeurs pilotes utilisent AmanaTrade de façon autonome
- Check-in hebdomadaire par WhatsApp (message ou appel)
- Suivi des métriques dans le back-office
- Traitement manuel de tout litige ouvert

### Semaines 7–8 — Débrief et synthèse
- Interviews de satisfaction : 20 vendeurs + 20 acheteurs minimum
- Dépouillement des métriques clés
- Rapport de validation terrain transmis au fondateur
- Décision : continuer en Phase 2 / pivoter / arrêter

---

## Métriques clés

| Métrique | Cible | Méthode de mesure |
|---|---|---|
| **Transactions complétées** | ≥ 30 | Logs système |
| **Taux d'activation vendeurs** (inscrit → ≥1 transaction) | ≥ 70 % | Logs système |
| **Taux de litiges ouverts** | < 20 % | Logs + suivi manuel |
| **Délai moyen de résolution des litiges** | ≤ 48h | Horodatage manuel |
| **Taux de confirmation acheteur avant expiration** | > 60 % | Logs système |
| **Score de satisfaction vendeurs** (1–5) | ≥ 3,5/5 | Questionnaire fin Phase 1 |
| **Score de satisfaction acheteurs** (1–5) | ≥ 3,5/5 | Questionnaire fin Phase 1 |
| **Ticket moyen constaté** | À mesurer | Logs transactions |
| **Taux de répétition vendeur** (≥2 transactions) | > 50 % | Logs système |
| **Recommandations spontanées** (nouveau vendeur via bouche-à-oreille) | ≥ 3 sur la période | Suivi manuel |

---

## Données à collecter impérativement

Ces données sont absentes des sources documentaires et doivent être récoltées lors du test :

| Donnée manquante | Pourquoi critique | Méthode |
|---|---|---|
| Ticket moyen réel transactions WhatsApp chaussures à Sabon Gari | Valider si l'AOV dépasse ₦20k (KYC Tier 2) | Interviews + données transactions pilote |
| Taux de refus de paiement à l'avance chez les acheteurs | Quantifier le problème principal | Interviews acheteurs |
| Tolérance réelle des vendeurs au délai 24h | Valider H05 | Interviews + observation |
| Volume mensuel estimé de transactions chaussures Sabon Gari | Dimensionner le marché adressable | Interviews vendeurs |
| Taux d'échec des virements bancaires chez les cibles (NIBSS) | UX tolérance aux erreurs | Données transactions pilote |
| Compatibilité OPay/PalmPay avec DVA NUBAN | Décision d'architecture PSP | Test technique |

---

## Risques du test terrain

| Risque | Probabilité | Impact | Mitigation |
|---|---|---|---|
| Absence de relais local disponible à Kano | Élevée | Critique — bloque tout | Prendre contact Startup Kano et Blue Sapphire Hub dès Phase 0 |
| Refus des vendeurs de fournir leur BVN | Moyenne | Élevé | Expliquer que le BVN ne donne pas accès au compte, c'est une vérification d'identité uniquement |
| Coupures Internet prolongées bloquant une transaction en cours | Moyenne | Moyen | Prévoir un protocole de déblocage manuel (contacter le PSP), communiquer sur les délais |
| Vendeurs pilotes abandonnent après les premières frictions | Moyenne | Élevé | Modèle concierge — présence humaine pour les premières transactions |
| Fraude intentionnelle d'un vendeur ou acheteur pilote | Faible | Élevé | Vérification BVN/NIN, limitation des montants Phase 1 (≤ ₦50 000 par transaction) |
| Problème de compatibilité PSP sandbox → production | Faible | Critique | Tester en sandbox avant Phase 1 — critère d'entrée non négociable |
| Données terrain insuffisantes (vendeurs réticents aux interviews) | Moyenne | Moyen | Questionnaires courts (<10 min), en haoussa, en face-à-face |

---

## Prérequis avant de lancer le test terrain

- [ ] Avocat nigérian CBN briefé et avis légal reçu sur l'architecture de paiement
- [ ] PSP choisi et testé en sandbox (DVA + Webhook + Disbursement fonctionnels)
- [ ] PWA développée et testée sur Android entrée de gamme (Tecno, Infinix) + réseau MTN
- [ ] Partenaire logistique confirmé (Peng Logistics ou Sendvoy)
- [ ] Relais local à Kano identifié et briefé
- [ ] Guide d'entretien vendeurs et acheteurs finalisé
- [ ] Budget Phase 1 confirmé (déplacement Kano, relais local, frais divers)
- [ ] Politique de litige minimale validée par le fondateur

---

*Responsable : Marketing & Operations Agent*
*Mis à jour : 2026-05-05 — après analyse recherche marché Kano*
*Action requise fondateur : Voyage à Kano, recrutement participants — voir HUMAN_ACTIONS.md*
*Sources : docs/08_research/market/reviewed/2026-05-05_kano-whatsapp-commerce-review.md*
