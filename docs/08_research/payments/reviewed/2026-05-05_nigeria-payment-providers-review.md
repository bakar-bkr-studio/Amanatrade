# Revue de Recherche : Fournisseurs de Paiement Nigeria — AmanaTrade

**Source analysée :** `docs/08_research/payments/raw/2026-05-05_nigeria-payment-providers.md`
**Date de revue :** 2026-05-05
**Révisé par :** Research Manager

---

## 1. Évaluation de la qualité de la recherche
**Qualité Globale : B+ (Très bonne base)**
- **Points forts :** Excellente profondeur technique (APIs, DVA, Split, Disbursement) et bonne couverture du contexte spécifique à Kano (USSD, MTN, Wakalah, Hausa-first). Sources primaires solides (CBN, Paystack, Monnify, etc.).
- **Faiblesses :** Aucune conclusion juridique définitive (nécessite validation avocat). Les comportements de Kano sont déduits de macro-données et d'études secondaires (nécessitent confirmation terrain). Tarifs APIs à revérifier en temps réel.

---

## 2. Faits confirmés utiles pour AmanaTrade

### Implications pour le paiement
- Le transfert bancaire direct est le canal dominant, mais souffre de la fraude "Audio Money" (fausses alertes).
- L'USSD est crucial pour les utilisateurs sans connexion internet ou avec des smartphones basiques.
- Les cartes bancaires (Visa/Mastercard) sont boudées pour les micro-transactions de social commerce en raison de la friction (OTP) et du manque de confiance.
- Les portefeuilles mobiles (OPay, PalmPay) sont massivement adoptés à Kano.

### Implications pour l’escrow ou escrow-like flow
- La détention directe de fonds tiers sur un compte corporate ("commingling") sans licence CBN est illégale.
- Les licences CBN (MMO, PSSP) requièrent un capital de 100M à 2B NGN, inatteignable pour le MVP.
- Le fractionnement (Split Payment) et le paiement différé (Disbursement/Single Transfer API) opérés via un partenaire licencié permettent de simuler un escrow sans que l'argent transite par le bilan comptable d'AmanaTrade.
- Les solutions d'Escrow-as-a-service existantes (Pandascrow, Vahlid) prennent 1.5% à 5% de frais, ce qui est trop coûteux pour ce segment.

### Implications pour le KYC/AML
- Le Tier 1 KYC de la CBN exige la collecte du BVN (Bank Verification Number) ou NIN (National Identity Number). C'est obligatoire avant de fournir des services financiers ou d'ouvrir un compte virtuel.
- Le coût de vérification d'un BVN est d'environ 10 NGN, et 60 NGN pour un NIN via Monnify.
- Le risque de blanchiment ("smurfing") et de fraude par identités synthétiques nécessite un monitoring comportemental (Machine Learning/scoring) à terme.

### Implications pour le choix du prestataire de paiement
- **Monnify** excelle avec des "Customer Reserved Accounts" (DVA permanents), des règlements biquotidiens (y compris week-ends), et des APIs de Split natives.
- **Squad (HabariPay)** offre les DVA les moins chers (0.25% plafonné à 1000 NGN).
- **Paystack** est rapide (Titan < 8s) mais plus cher pour les DVA et les micro-transactions.
- **Korapay** propose une API unifiée incluant OPay et PalmPay.

### Implications pour le MVP
- Le MVP doit être une PWA (Progressive Web App) "Offline-First" optimisée pour le réseau MTN.
- Intégration vitale via la Web Share API (`navigator.share()`) pour s'insérer naturellement dans les conversations WhatsApp.
- Interface "Hausa-First" (termes comme *Ciniki*, *Wakala*) pour réduire la charge cognitive et créer un sentiment de confiance.
- Le KYC (BVN/NIN) doit être introduit de manière asynchrone (uniquement au moment de l'engagement financier, pas au premier téléchargement).

---

## 3. Hypothèses
- **H1 :** L'architecture Split + Disbursement via un PSP licencié est légalement considérée comme exempte de licence CBN pour l'opérateur (AmanaTrade).
- **H2 :** Le modèle contractuel de *Wakalah* (agence) sera perçu favorablement par les utilisateurs de Kano et atténuera la perception d'usure.
- **H3 :** Les vendeurs seront prêts à payer une commission de service (malgré l'habitude de transferts gratuits) pour éviter les fraudes et garantir le paiement.
- **H4 :** Les DVA permanents (Reserved Accounts) offriront un meilleur taux de complétion de paiement que les comptes virtuels dynamiques (à expiration).
- **H5 :** OPay et PalmPay permettent des virements sans friction vers les DVA NUBAN de Monnify ou Squad.

---

## 4. Risques
- **Légal (Critique) :** Que la CBN considère l'orchestration Split/Disbursement comme une forme illégale de "commingling" ou comme nécessitant une licence PSSP.
- **Conformité (Élevé) :** Gel des APIs par le PSP partenaire si les contrôles KYC/AML d'AmanaTrade sont jugés insuffisants ou si un trafic de blanchiment est détecté.
- **Technique (Moyen) :** Retards structurels du réseau interbancaire NIBSS qui empêcheraient la confirmation en temps réel du paiement, ruinant l'expérience sur WhatsApp.
- **Opérationnel (Élevé) :** Mauvaise foi des acheteurs ou vendeurs (litiges, fausses déclarations d'expédition ou de non-réception) nécessitant une charge de modération manuelle trop lourde.

---

## 5. Questions ouvertes
- La structure technique Split+Disbursement est-elle *strictement* conforme légalement sans licence propre ? (Opinion écrite d'un avocat requise)
- Quel sera le taux de commission optimal pour équilibrer rentabilité et adoption par les vendeurs ?
- Le positionnement contractuel et marketing "Wakalah" a-t-il une valeur juridique défendable devant les tribunaux et les autorités religieuses nigérianes ?
- OPay/PalmPay sont-ils totalement compatibles avec les DVA Monnify/Squad, sans surcoûts ou blocages de portefeuilles fermés ?
- Quelles sont les conditions exactes d'onboarding (KYB, volume) pour qu'une nouvelle startup utilise les APIs de Monnify et Squad ?

---

## 6. Recommandations
1. **Légal :** Soumettre l'architecture technique (Hold & Release via PSP) à un avocat nigérian spécialisé en réglementation CBN pour une opinion légale formelle.
2. **Technique :** Sélectionner **Monnify** ou **Squad** comme cibles principales. Effectuer des tests POC (Proof of Concept) en sandbox pour valider les flux DVA, les paiements via OPay, et la Disbursement API.
3. **Produit :** Concevoir le flux utilisateur principal uniquement autour des transferts de compte à compte via DVA automatisés, sans intégration de cartes bancaires.
4. **UX/UI :** Prioriser l'intégration native WhatsApp (Web Share API) et adopter une architecture d'information "Hausa-First" pour baisser les barrières à l'entrée.
5. **Stratégie (Phase 1) :** Conduire les interviews terrain à Kano pour vérifier l'appétence à payer (commission vs protection) et les perceptions des délais de virement.
