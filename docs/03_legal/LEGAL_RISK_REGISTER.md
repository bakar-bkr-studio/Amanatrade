# LEGAL RISK REGISTER — AmanaTrade

## Objectif de ce document
Recenser et prioriser tous les risques légaux et réglementaires identifiés pour AmanaTrade au Nigeria.

---

## Format d'entrée

```
### [ID] [DOMAINE] — Titre du risque
**Description :** Ce qui pourrait poser un problème légal.
**Probabilité :** Élevée / Moyenne / Faible
**Impact :** Élevé / Moyen / Faible
**Réglementation concernée :** Loi, article, régulateur.
**Statut de l'analyse :** Confirmé / À vérifier / Incertain
**Mitigation possible :** Ce qui peut être fait pour réduire le risque.
**Action requise :** Voir HUMAN_ACTIONS.md / QUESTIONS_FOR_LAWYER.md
```

---

## Risques identifiés

### R001 [PAIEMENTS] — Licence CBN pour service d'escrow ou détention de fonds
**Description :** Toute détention directe de fonds de tiers sans licence CBN (MMO ou PSSP) est explicitement interdite. Licence MMO = 2 milliards NGN de capital minimum. Licence PSSP = 100 millions NGN. Inatteignable pour le MVP.
**Probabilité :** Élevée si architecture incorrecte (fonds sur compte bancaire AmanaTrade)
**Impact :** Critique — gel des avoirs, sanctions CBN, fermeture forcée
**Réglementation concernée :** CBN Payment Service Providers Regulations, CBN Guidelines Payment Service Holding Companies
**Statut de l'analyse :** Partiellement analysé (recherche). ⚠️ À confirmer par avocat nigérian.
**Mitigation possible :** Utiliser l'architecture Hold & Release via PSP licencié (Monnify/Squad/Flutterwave) — fonds dans les sous-comptes du PSP, jamais sur le compte AmanaTrade.
**Action requise :** QUESTIONS_FOR_LAWYER.md + HUMAN_ACTIONS.md (trouver avocat CBN fintech)

---

### R002 [KYC/AML] — Exigences d'identification des utilisateurs (BVN/NIN)
**Description :** Le Tier 1 KYC CBN impose désormais une liaison BVN ou NIN obligatoire avant tout accès aux services de paiement. Un utilisateur sans BVN/NIN ne peut pas réaliser de transaction.
**Probabilité :** Certaine — c'est une exigence réglementaire non optionnelle
**Impact :** Élevé — risque d'exclusion d'une partie des utilisateurs cibles non bancarisés
**Réglementation concernée :** CBN Customer Due Diligence Regulations 2023, MLPPA 2022
**Statut de l'analyse :** Confirmé par la recherche (sources CBN + Youverify 2026). ⚠️ Interprétation de la portée à valider par avocat.
**Mitigation possible :** KYC progressif : exploration de la PWA sans contrainte, vérification BVN/NIN uniquement au moment de la première transaction financière. Utiliser l'API Monnify (BVN ~10 NGN, NIN ~60 NGN).
**Action requise :** QUESTIONS_FOR_LAWYER.md

---

### R003 [DONNÉES] — Conformité NDPR (Nigeria Data Protection Regulation)
**Description :** Collecte de données personnelles (BVN, NIN, photos de livraison, conversations) soumise à la NDPR 2019.
**Probabilité :** Élevée — toute collecte de données personnelles au Nigeria est soumise
**Impact :** Moyen — amende et atteinte à la réputation
**Réglementation concernée :** Nigeria Data Protection Regulation (NDPR) 2019, Nigeria Data Protection Act 2023
**Statut de l'analyse :** À vérifier. ⚠️ À valider par avocat.
**Mitigation possible :** Politique de confidentialité conforme, consentement explicite, stockage données minimal, hébergement préférable sur serveurs Nigeria ou UE.
**Action requise :** QUESTIONS_FOR_LAWYER.md

---

### R004 [PAIEMENTS] — Risque de commingling des fonds
**Description :** Si l'architecture technique permet, même temporairement, un mélange des fonds des clients avec les fonds opérationnels d'AmanaTrade (compte bancaire corporate), cela constitue un "commingling" explicitement interdit par la CBN. Des PSP pourraient également geler les intégrations API si ce risque est détecté.
**Probabilité :** Moyenne — dépend de l'implémentation technique
**Impact :** Critique — sanctions CBN + gel des APIs PSP partenaires
**Réglementation concernée :** CBN Guidelines for Payments Service Holding Companies (règle anti-commingling)
**Statut de l'analyse :** Risque identifié par la recherche. ⚠️ Architecture technique à valider par avocat.
**Mitigation possible :** Fonds toujours dans l'environnement du PSP licencié. Jamais de transfert intermédiaire vers un compte AmanaTrade. Audit log de toutes les transactions.
**Action requise :** QUESTIONS_FOR_LAWYER.md + revue technique de l'architecture par le Tech Architecture Agent

---

### R005 [AML/FRAUDE] — Risque de smurfing et d'identités synthétiques
**Description :** Des acteurs malveillants pourraient utiliser AmanaTrade pour blanchir des fonds via des micro-transactions (smurfing) ou créer des comptes avec des BVN/NIN volés (identités synthétiques). En 2024, la CBN a fermé plusieurs comptes de startups pour facilitation de fraude.
**Probabilité :** Moyenne — risque inhérent à toute plateforme de paiement
**Impact :** Critique — gel de l'intégration API, sanctions EFCC, dommages réputationnels
**Réglementation concernée :** MLPPA 2022, CBN AML/CFT Regulations, EFCC Act
**Statut de l'analyse :** Risque identifié par la recherche.
**Mitigation possible :** Surveillance comportementale automatisée (fréquence, montants atypiques), scoring de risque, double vérification BVN+correspondance nom/téléphone, seuils transactionnels Tier 1 respectés.
**Action requise :** QUESTIONS_FOR_LAWYER.md + à implémenter dans l'architecture technique (Phase 2)

---

### R006 [CONTRATS] — Statut juridique du modèle Wakalah au Nigeria
**Description :** Le rapport de recherche suggère de structurer contractuellement le service AmanaTrade comme un contrat d'agence islamique (Wakalah) pour la compatibilité sharia. Ce cadre n'a pas été validé par un juriste islamique nigérian ni par les autorités religieuses locales.
**Probabilité :** Faible que ce soit un blocage immédiat, mais incertain à long terme
**Impact :** Moyen — si contesté, atteinte à la confiance des utilisateurs de Kano
**Réglementation concernée :** Pas de réglementation CBN spécifique. Relève du droit contractuel privé et des principes de finance islamique.
**Statut de l'analyse :** Hypothèse non vérifiée. ⚠️ À valider par expert en finance islamique nigérian.
**Mitigation possible :** Consulter un expert en finance islamique (scholar) nigérian. Tester la perception terrain lors des interviews Phase 1.
**Action requise :** QUESTIONS_FOR_LAWYER.md (mention spécifique finance islamique) + interviews terrain

---

### R007 [STRUCTURE LÉGALE] — Absence de filiale nigériane (CAMA 2020)
**Description :** La loi CAMA 2020 interdit à toute société étrangère de mener des affaires au Nigeria sans créer une filiale locale enregistrée auprès de la Corporate Affairs Commission (CAC). Le capital social minimum pour une société à participation étrangère est de **100 millions NGN**.
**Probabilité :** Certaine si AmanaTrade recrute des utilisateurs et traite des paiements au Nigeria
**Impact :** Critique — activité illégale sans CAC. Bloque également l'accès aux licences CBN, aux comptes bancaires nigérians et aux contrats PSP
**Réglementation concernée :** CAMA 2020, NIPC Act
**Statut de l'analyse :** Confirmé par la recherche. ⚠️ Priorité et timing à valider par avocat.
**Mitigation possible :** Enregistrer une filiale CAC avant tout lancement commercial. Évaluer si la phase pilote peut être menée sous une structure d'agent ou de partenariat.
**Action requise :** QUESTIONS_FOR_LAWYER.md + HUMAN_ACTIONS.md

---

### R008 [LITIGES] — Conflit de juridiction Charia / Cour fédérale à Kano
**Description :** À Kano, les tribunaux de la Charia ont compétence pour les litiges commerciaux (*Mu'amalat*) entre Musulmans. Les litiges impliquant des institutions financières agréées relèvent souvent de la Haute Cour Fédérale. Des contrats mal rédigés peuvent créer des conflits de compétence imprévisibles et coûteux.
**Probabilité :** Moyenne — dépend de la rédaction des CGU et de la nature du litige
**Impact :** Moyen à Élevé — litiges longs, décisions imprévisibles, atteinte à la réputation
**Réglementation concernée :** Charia courts (Kano State), Federal High Court, FCCPA 2018
**Statut de l'analyse :** Confirmé par sources académiques. ⚠️ Clause de juridiction à valider par avocat local Kano.
**Mitigation possible :** Rédiger les CGU avec une clause de juridiction explicite. Consulter un avocat nigérian connaissant le droit de Kano. Envisager une clause d'arbitrage (ADR) comme tiers choisi.
**Action requise :** QUESTIONS_FOR_LAWYER.md

---

### R009 [DONNÉES] — Non-conformité NDPA 2023 : DPO + audit annuel DPCO
**Description :** La NDPA 2023 exige pour les fintechs : (1) la nomination d'un DPO (Délégué à la Protection des Données), (2) l'enregistrement auprès de la NDPC dès que l'organisation traite les données de plus de 200 personnes sur 6 mois, (3) un audit annuel de conformité via une organisation DPCO certifiée.
**Probabilité :** Certaine dès que le MVP dépasse 200 utilisateurs
**Impact :** Moyen — amende jusqu'à 2 % du CA annuel ou 10 M NGN
**Réglementation concernée :** Nigeria Data Protection Act 2023, NDPC Guidance Notice 2024
**Statut de l'analyse :** Confirmé. ⚠️ Coûts et procédures exacts à vérifier.
**Mitigation possible :** Anticiper la désignation d'un DPO (peut être externe). Préparer l'enregistrement NDPC avant les 200 premiers utilisateurs. Identifier une DPCO certifiée.
**Action requise :** HUMAN_ACTIONS.md (anticiper avant lancement MVP)

---

### R010 [DONNÉES] — Transfert de données Nigeria → France sans adéquation NDPC
**Description :** La NDPA 2023 interdit le transfert de données personnelles nigérianes vers un pays tiers sans décision d'adéquation ou clauses contractuelles types approuvées par la NDPC. La décision d'adéquation pour la France (sous RGPD) est en cours de mise à jour 2025 — pas encore confirmée.
**Probabilité :** Élevée — fondateur basé en France, accès aux données depuis France probable
**Impact :** Élevé — amende NDPA + blocage réglementaire
**Réglementation concernée :** NDPA 2023 Art. 7 (transferts transfrontaliers), NDPC 2025
**Statut de l'analyse :** Risque confirmé par la recherche. ⚠️ Statut exact de la liste d'adéquation à vérifier.
**Mitigation possible :** Utiliser des clauses contractuelles types approuvées par la NDPC pour encadrer l'accès depuis la France. Minimiser les accès distants aux données personnelles. Privilégier l'hébergement Nigeria.
**Action requise :** QUESTIONS_FOR_LAWYER.md + architecture technique à adapter

---

### R011 [PAIEMENTS] — KYC Tier 1 : plafond de ₦20 000 par transaction
**Description :** Le KYC CBN Tier 1 limite les dépôts à ₦20 000 par transaction et ₦200 000 en solde cumulé. Si le ticket moyen des transactions vêtements/chaussures à Kano dépasse ₦20 000 (~12–15 €), les acheteurs devront passer au Tier 2 (pièce d'identité officielle vérifiée), augmentant la friction à l'onboarding.
**Probabilité :** Moyenne — dépend du ticket moyen réel terrain (non encore validé)
**Impact :** Élevé sur l'adoption — friction onboarding, exclusion d'une partie des transactions
**Réglementation concernée :** CBN Customer Due Diligence Regulations 2023, KYC TMT Update 2024
**Statut de l'analyse :** Confirmé (règle KYC). ⚠️ Ticket moyen réel à valider terrain.
**Mitigation possible :** Concevoir le produit pour Tier 1 (≤ ₦20 000) par défaut. Prévoir un flux Tier 2 optionnel pour tickets plus élevés. Valider le ticket moyen lors des interviews terrain Phase 1.
**Action requise :** Validation terrain (HUMAN_ACTIONS.md) + RESEARCH_BACKLOG.md

---

### R012 [STRUCTURE LÉGALE] — Lettre de non-objection CBN non obtenue
**Description :** La CBN exige que les fintechs obtiennent une autorisation préalable ou une lettre de "non-objection" avant de lancer des services en partenariat avec des institutions financières. Lancer sans cette lettre expose à une cessation forcée d'activité.
**Probabilité :** Élevée si partnership PSP lancé sans vérification préalable
**Impact :** Critique — blocage réglementaire, fermeture forcée, dommages partenaire PSP
**Réglementation concernée :** CBN Regulatory Framework for Finance Companies 2014 (révisé), CBN circulaires PSP
**Statut de l'analyse :** Confirmé que la lettre est exigée. ⚠️ Procédure exacte, délais et conditions à valider par avocat.
**Mitigation possible :** Obtenir la lettre de non-objection AVANT de signer un contrat avec un PSP. Consulter un avocat nigérian pour guider la procédure.
**Action requise :** QUESTIONS_FOR_LAWYER.md + HUMAN_ACTIONS.md

---

### R013 [FISCAL] — CCI (Capital Import Certificate) non obtenu
**Description :** Tout capital étranger injecté au Nigeria doit faire l'objet d'un Certificat d'Importation de Capitaux (CCI) émis par la banque réceptrice dans les 24–48h. Sans CCI, il est illégal de rapatrier des dividendes ou bénéfices via le marché officiel des changes.
**Probabilité :** Élevée si le fondateur injecte du capital sans passer par une banque nigériane habilitée
**Impact :** Moyen — bloque le retour sur investissement. N'empêche pas l'activité opérationnelle.
**Réglementation concernée :** CBN Foreign Exchange (Monitoring & Miscellaneous Provisions) Act, NIPC Act
**Statut de l'analyse :** Confirmé. ⚠️ Procédure exacte et banque habilitée à identifier.
**Mitigation possible :** Passer toute injection de capital via une banque nigériane habilitée qui émet le CCI automatiquement. Ne pas injecter de capital en cash ou via des transferts informels.
**Action requise :** HUMAN_ACTIONS.md (avant toute injection de capital)

---

## Risques à analyser
- Régime de taxation des services numériques (VAT 7,5 % sur services fintech Nigeria) — impacte le modèle de commission
- Obligations de reporting fiscal des vendeurs utilisant AmanaTrade (FIRS)
- Vérification physique d'adresse Tier 1 (mise à jour CBN juin 2024) — qui la réalise pour AmanaTrade ?

---

*Responsable : Legal & Compliance Agent*
*Sources : `docs/08_research/payments/reviewed/2026-05-05_nigeria-payment-providers-review.md` + `docs/08_research/legal/reviewed/2026-05-05_nigeria-escrow-regulation-review.md`*
*Dépendances : docs/08_research/legal/, QUESTIONS_FOR_LAWYER.md*
*Mis à jour le : 2026-05-05*

