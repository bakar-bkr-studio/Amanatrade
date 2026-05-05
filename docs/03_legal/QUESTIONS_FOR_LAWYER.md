# QUESTIONS FOR LAWYER — AmanaTrade

## Objectif de ce document
Préparer une liste de questions précises et hiérarchisées pour la consultation avec un avocat spécialisé en droit des affaires et fintech au Nigeria.

---

## Profil avocat cible
- Spécialisation : Droit des paiements électroniques / Fintech / CBN regulation
- Expérience : Startups fintech Nigeria, idéalement Kano ou Abuja/Lagos
- *À recruter — voir HUMAN_ACTIONS.md*

---

## Questions prioritaires (🔴 Bloquantes pour le MVP)

### Sur le mécanisme d'escrow (Split + Disbursement)
1. **Légalité du modèle indirect :** AmanaTrade prévoit d'utiliser les APIs d'un Payment Service Provider (PSP) licencié (comme Monnify ou Squad) pour diviser (Split) les paiements et retenir les fonds dans un sous-compte géré par le PSP. AmanaTrade ne détient jamais l'argent sur son propre compte, mais déclenche la libération (Disbursement) par appel API. Ce modèle nous exempte-t-il légalement de posséder une licence MMO ou PSSP de la CBN ?
2. **Commingling :** Cette architecture d'orchestration via API présente-t-elle un risque d'être qualifiée de "commingling" (mélange de fonds) par la CBN, même si l'argent reste dans les systèmes du PSP ?
3. **Contrat Wakalah :** L'utilisation du cadre contractuel de *Wakalah* (agence) dans nos CGU pour justifier nos commissions (Ujrah) offre-t-elle une protection légale supplémentaire, ou est-ce purement marketing ? Ce modèle est-il reconnu par les tribunaux nigérians ?

### Sur les licences CBN
1. **Opérer sans licence :** Existe-t-il d'autres licences ou enregistrements obligatoires (ex: Agent Banking, Value Added Services) pour opérer ce service d'orchestration depuis une entité non licenciée (voire une entité étrangère) ?
2. **Sanctions :** Quelles sont les pénalités si la CBN qualifie par la suite notre modèle d'activité financière non réglementée ?

### Sur le KYC/AML
1. **Exigences Tier 1 :** Confirmons-nous que la réglementation CBN actuelle (Customer Due Diligence Regulations 2023) exige la vérification obligatoire du BVN ou NIN avant toute transaction financière, même pour des montants minimes ?
2. **Responsabilité AML :** En tant qu'orchestrateur (les fonds transitant chez Monnify/Squad), AmanaTrade a-t-il les mêmes obligations de déclaration de transactions suspectes qu'une institution financière licenciée ?

---

### Sur la lettre de non-objection CBN
1. **Procédure exacte :** Quelle est la procédure pour obtenir une lettre de "non-objection" (no-objection letter) de la CBN avant de lancer un service fintech en partenariat avec un PSP licencié ? Quels sont les délais réalistes (semaines ? mois ?) et les documents requis ?
2. **Timing :** Cette lettre est-elle requise avant la signature du contrat avec le PSP, ou uniquement avant le lancement commercial ?
3. **Phase pilote :** Une lettre de non-objection est-elle requise pour une phase de test avec un nombre limité d'utilisateurs (< 50 vendeurs) ?

---

## Questions importantes (🟡 Importantes mais non bloquantes à court terme)

### Sur la structure juridique de la société (CAMA 2020)
1. **CAC Registration :** La loi CAMA 2020 exige une filiale locale pour toute société étrangère opérant au Nigeria. Le capital social minimum est de 100 millions NGN pour une participation étrangère. Pouvons-nous lancer la phase pilote sans filiale, ou l'enregistrement CAC est-il un prérequis absolu même pour un test à petite échelle ?
2. **Capital minimum :** Le capital de 100 M NGN doit-il être entièrement libéré dès la création de la filiale, ou peut-il être versé progressivement ? Quelle est la méthode optimale pour minimiser les droits d'enregistrement (0,75 % du capital) ?
3. **Directeur résident :** CAMA 2020 exige-t-il un directeur résident nigérian ? Quels sont les risques en l'absence d'un directeur local ?
4. **TVA (VAT) :** Les commissions facturées par AmanaTrade aux vendeurs nigérians sont-elles soumises à la TVA nigériane (7,5%), même sans entité locale ? Cela change-t-il avec une filiale CAC ?

### Sur la protection des données (NDPA 2023)
1. **Localisation des données :** La NDPA 2023 nous oblige-t-elle à héberger les données des utilisateurs nigérians (noms, téléphones, BVN/NIN, photos de livraison) sur des serveurs physiquement situés au Nigeria ?
2. **Transfert Nigeria → France :** En l'absence de décision d'adéquation formelle pour la France, quelles clauses contractuelles types approuvées par la NDPC devons-nous utiliser pour permettre l'accès aux données depuis la France (fondateur, équipe technique) ?
3. **NDPC enregistrement :** À partir de combien d'utilisateurs l'enregistrement auprès de la NDPC devient-il obligatoire ? Quels sont les délais et les coûts estimés ?
4. **DPO :** Un DPO externe peut-il être désigné, ou doit-il être un employé interne ? Quel est le coût estimé d'un DPO externe qualifié au Nigeria ?

### Sur les litiges à Kano
1. **Juridiction :** Comment rédiger la clause de juridiction dans les CGU pour qu'elle soit valide à la fois pour les utilisateurs Musulmans de Kano (potentiellement sous juridiction Charia) et pour les utilisateurs non-Musulmans ou les litiges impliquant une institution financière ? Une clause d'arbitrage (ADR) est-elle préférable ?
2. **CGU en haoussa :** Une clause rédigée en haoussa mais non traduite en anglais est-elle juridiquement opposable devant les tribunaux nigérians ?
3. **Responsabilité litige :** Si AmanaTrade libère des fonds au vendeur mais que l'acheteur prouve ensuite une fraude, AmanaTrade peut-elle être tenue légalement responsable du remboursement ?

### Sur le rapatriement des bénéfices (CCI)
1. **CCI :** Comment le fondateur (basé en France) doit-il procéder pour obtenir un Certificat d'Importation de Capitaux (CCI) lors d'une injection de capital dans la filiale nigériane ? Quelle banque nigériane peut émettre ce certificat ?
2. **WHT :** La retenue à la source (WHT) de 10 % sur les dividendes s'applique-t-elle même dans le cadre de la convention fiscale Nigeria–France ?

### Sur le Nigeria Startup Act 2022
1. **Startup Label :** L'obligation de 33,3 % de capital nigérian est-elle calculée sur le capital total ou sur les droits de vote ? Un investisseur minoritaire de la diaspora haoussa suffirait-il ?
2. **Avantages concrets :** L'exonération fiscale de 4 ans s'applique-t-elle aux commissions encaissées ou uniquement aux bénéfices nets ?

---

## Questions utiles (🟢 À traiter dans un second temps)

- Existe-t-il une jurisprudence récente (depuis 2024) où la CBN a sanctionné des startups utilisant des sous-comptes chez des PSP sans licence propre ?
- Le modèle Trust Account (Option E) offre-t-il une protection légale supérieure à l'architecture Split+Disbursement (Option B) ?
- La KSCPC (Kano State Consumer Protection Council) a-t-elle des obligations spécifiques pour les plateformes e-commerce opérant dans l'État de Kano ?

---

## Résultats de la consultation
> *À remplir après la réunion avec l'avocat — avec date et nom du cabinet*

---

*Responsable : Legal & Compliance Agent*
*Action requise : HUMAN_ACTIONS.md — Trouver et contacter un avocat fintech Nigeria*
*Mis à jour le : 2026-05-05*
