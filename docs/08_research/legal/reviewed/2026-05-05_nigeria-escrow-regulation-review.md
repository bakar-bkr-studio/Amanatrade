# RESEARCH REVIEW — Cadre réglementaire nigérian : escrow, paiements, données, structure légale

**Fichier source :** `docs/08_research/legal/raw/2026-05-05_nigeria-escrow-regulation.md`
**Revue par :** Research Manager + Legal & Compliance Agent + Tech Architecture Agent
**Date de revue :** 2026-05-05
**Niveau de fiabilité global :** ⚠️ B+ — Sources primaires et secondaires solides, mais aucun avis d'avocat nigérian qualifié obtenu. Les interprétations réglementaires restent des hypothèses jusqu'à validation.

---

## 1. Évaluation de la qualité de la recherche

### Sources utilisées
- 52 sources référencées
- Sources primaires (Niveau A) : CBN.gov.ng, NDPC.gov.ng, NJI.gov.ng, CBN PSV2025, CBN KYC circulaires, KPMG Nigeria, PwC Nigeria, ResearchGate (juridique peer-reviewed) → ✅ Fiables
- Sources secondaires (Niveau B) : Lawzana, Manifield Solicitors, DOA Law, Templars Law → ⚠️ Fiables pour l'orientation, pas pour les conclusions définitives
- Sources tertiaires (Niveau C) : Prifinance, Lucid.now, Kabbiz Global → ⚠️ À confirmer

### Faiblesses identifiées
1. Aucune confirmation directe d'un avocat nigérian spécialisé CBN. Tout est secondaire.
2. La tolérance CBN envers les architectures Split+Disbursement sans licence est une inférence de pratique de marché, pas une décision réglementaire explicite.
3. Les données sur les délais et procédures (CCI, NDPC) peuvent évoluer rapidement.
4. Certaines sources datent de 2021–2022 — à reverifier pour les montants de capital (potentiellement révisés).

---

## 2. Faits confirmés ✅

### 2.1 Licences CBN — Détention de fonds
| Fait | Détail | Niveau source |
|---|---|---|
| ✅ MMO = seule entité pouvant détenir fonds clients | Capital minimum : **2 milliards NGN** + dépôt de garantie 2 Md NGN à CBN | A (CBN circulaire 2020/2021) |
| ✅ PSSP ne peut PAS détenir fonds clients | PSSP = passerelle paiement uniquement. Capital minimum : **100 millions NGN** | A (CBN circulaire 2020/2021) |
| ✅ Règle anti-commingling | Interdit explicitement le mélange fonds clients / fonds opérationnels pour toute entité | A (CBN) |
| ✅ Opérer un service de détention de fonds sans licence = activité bancaire illégale | Sanctions pénales + gel des comptes | A (CBN) |
| ✅ Escrow reconnu juridiquement au Nigeria | Mécanisme légal de tiers de confiance, mais exige banque partenaire ou MMO pour détenir les fonds | B (Pavestone Legal) |
| ✅ CBN exige "lettre de non-objection" | Avant tout lancement de service fintech en partenariat avec institution financière | B (Prifinance) |

### 2.2 KYC / AML
| Fait | Détail | Niveau source |
|---|---|---|
| ✅ BVN ou NIN obligatoire dès Tier 1 | Vérification obligatoire avant toute transaction financière | A (CBN KYC/AML 2023, Youverify 2026) |
| ✅ Tier 1 KYC : limite ₦20 000 par dépôt | Limite cumulée : ₦200 000. Pas de pièce d'identité officielle requise, juste BVN/NIN + téléphone | A (DOA Law KYC TMT 2024) |
| ✅ Tier 2 : limite ₦50 000 / dépôt | ₦500 000 cumulé. Pièce d'identité officielle vérifiée requise | A |
| ✅ Vérification physique d'adresse requise même Tier 1 | Mise à jour CBN juin 2024. Contrainte logistique majeure pour opération à distance | A (DOA Law 2024) |
| ✅ Signalement à la NFIU sous 24h | Toute transaction suspecte doit être signalée à l'Unité de Renseignement Financier du Nigeria | A (CBN AML/CFT) |

### 2.3 NDPA 2023 — Protection des données
| Fait | Détail | Niveau source |
|---|---|---|
| ✅ NDPA 2023 est la loi de référence | Remplace NDPR 2019. Sanctions : jusqu'à 2 % du CA annuel ou 10 M NGN | A (KPMG, Cookie-Script) |
| ✅ Enregistrement NDPC obligatoire | Dès lors que l'organisation traite les données de plus de **200 personnes sur 6 mois** | A (NDPC Guidance Notice 2024) |
| ✅ DPO obligatoire pour fintechs | Les "Data Controllers of Major Importance" (catégorie incluant les fintechs) doivent nommer un DPO | A (NDPC) |
| ✅ Audit annuel DPCO obligatoire | À déposer chaque année via une organisation de conformité certifiée (DPCO) | A (DLA Piper) |
| ✅ Transfert Nigeria → France : pas encore d'adéquation formelle confirmée | NDPA exige adéquation ou clauses contractuelles types. Liste en cours de mise à jour 2025 | B (OTL Law) |

### 2.4 Structure légale (CAMA 2020)
| Fait | Détail | Niveau source |
|---|---|---|
| ✅ Société étrangère DOIT créer filiale locale | Registre CAC obligatoire pour opérer au Nigeria | A (CAMA 2020, Kabbiz Global) |
| ✅ Capital social minimum filiale étrangère : 100 millions NGN | Base de calcul des droits d'enregistrement (0,75 % du capital) | A (CAMA 2020) |
| ✅ Enregistrement NIPC obligatoire | Pour protection de l'investissement et droit de rapatriement des bénéfices | A |

### 2.5 Fiscalité & Rapatriement
| Fait | Détail | Niveau source |
|---|---|---|
| ✅ CCI (Certificat d'Importation de Capitaux) obligatoire | Émis par la banque réceptrice sous 24–48h lors d'injection de capital. Sans CCI : rapatriement impossible via marché officiel | A (Templars Law) |
| ✅ WHT (retenue à la source) sur dividendes : 10 % | Taux standard depuis l'abrogation du taux préférentiel 7,5 % en juillet 2022 | A (KPMG FIRS) |
| ✅ Convention fiscale Nigeria–France existe | Évite la double imposition, mais WHT 10 % s'applique quand même | A (KPMG) |

### 2.6 Nigeria Startup Act 2022
| Fait | Détail | Niveau source |
|---|---|---|
| ✅ Startup Label exige ≥ 33,3 % capital nigérian | Condition de propriété pour bénéficier des avantages du Startup Act | A (Balogun Harold) |
| ✅ Avantages : exonération fiscale 4 ans, crédits d'impôt investisseurs, accès facilité aux licences | Via portail NITDA dédié | A (UHY Maaji) |

### 2.7 Litiges & Protection des consommateurs
| Fait | Détail | Niveau source |
|---|---|---|
| ✅ FCCPA 2018 = loi fédérale protection consommateur | Protège contre pratiques déloyales, publicités mensongères, produits défectueux | A (Manifield) |
| ✅ Kano State Consumer Protection Council (KSCPC) restructuré 2025 | Actif sur les marchés de textiles et chaussures | A (Daily Post, Rural Development Kano) |
| ✅ Tribunaux Charia compétents pour litiges commerciaux entre Musulmans à Kano | Compétence *Mu'amalat* (droit commercial islamique) | A (NJI, ResearchGate) |
| ✅ Conflits de juridiction Charia/Cour fédérale possibles | Si contrats mal rédigés, risque de conflit de compétence | A (ResearchGate) |

---

## 3. Hypothèses ⚠️ (non confirmées par avocat)

| Hypothèse | Niveau de confiance | À valider par |
|---|---|---|
| H1 : Architecture Split+Disbursement via PSP = exempte de licence CBN propre | ⚠️ Moyen — pratique de marché observée, pas de décision CBN explicite | Avocat nigérian CBN |
| H2 : Compte fiduciaire bancaire = alternative légale à la détention directe | ⚠️ Moyen — mentionné dans doctrine, non validé formellement | Avocat nigérian CBN |
| H3 : Wakalah structure = protection légale suffisante pour les commissions | ⚠️ Faible — mentionné comme piste, pas de jurisprudence citée | Avocat + scholar islamique |
| H4 : France sera reconnue "adéquate" par NDPC en 2025 | ⚠️ Faible — processus en cours, pas encore actif | Suivi NDPC + avocat |
| H5 : Pas de licence nécessaire pour lancer une phase pilote non-commerciale | ❌ Non confirmé | Avocat |
| H6 : CBN tolère le modèle sans lettre de non-objection en phase de test | ❌ Non confirmé | Avocat |

---

## 4. Risques juridiques identifiés

### 🔴 Risques critiques — Bloquants immédiats

| ID | Risque | Impact |
|---|---|---|
| RL-01 | Détention directe de fonds sans licence MMO | Sanctions pénales, gel comptes |
| RL-02 | Opérer au Nigeria depuis société étrangère sans filiale CAC | Illégal sous CAMA 2020 |
| RL-03 | Lancement sans lettre de non-objection CBN | Blocage réglementaire, fermeture forcée |
| RL-04 | Architecture Split non validée = risque commingling | Sanctions CBN + gel APIs PSP partenaires |

### 🟡 Risques importants

| ID | Risque | Impact |
|---|---|---|
| RL-05 | KYC Tier 1 : limite ₦20 000/transaction | Plafonne les transactions MVP à ~12 € — validation terrain requise |
| RL-06 | Vérification physique adresse Tier 1 (juin 2024) | Logistique complexe pour onboarding à distance |
| RL-07 | Transfert données Nigeria → France sans adéquation NDPC | Amende NDPA + risque reputationnel |
| RL-08 | Conflit de juridiction Charia/Cour fédérale à Kano | Litiges complexes et imprévisibles |
| RL-09 | CCI non obtenu = rapatriement impossible | Bloque le retour sur investissement du fondateur |
| RL-10 | Enregistrement NDPC requis dès 200 utilisateurs | Délai et coût à anticiper dès le MVP |

### 🟢 Risques de fond

| ID | Risque | Impact |
|---|---|---|
| RL-11 | WHT 10 % sur dividendes | Réduction de la rentabilité pour le fondateur |
| RL-12 | Startup Label nécessite 33,3 % capital nigérian | Oblige à impliquer un co-fondateur ou investisseur nigérian |
| RL-13 | Pas de DPO nommé = non-conformité NDPA | Amende NDPA |

---

## 5. Implications pour AmanaTrade

### 5.1 Détention de fonds — Modèle à retenir
**Conclusion de la recherche :** AmanaTrade ne peut en aucun cas détenir les fonds des acheteurs sur son propre compte bancaire, même temporairement. Deux architectures alternatives sont viables :

**Architecture A (recommandée) — Split+Disbursement via PSP licencié**
- Fonds retenus dans l'infrastructure du PSP (Monnify, Squad)
- AmanaTrade est orchestrateur logique uniquement
- Risque : non explicitement validé par CBN — à confirmer par avocat
- *Voir `docs/05_tech/PAYMENT_FLOW.md` pour le flux technique*

**Architecture B (alternative) — Compte fiduciaire bancaire (Trust Account)**
- Fonds versés par l'acheteur sur un compte fiduciaire ouvert auprès d'une banque commerciale partenaire
- AmanaTrade a un pouvoir d'instruction par API (pas de détention directe)
- Potentiellement plus solide légalement, mais plus complexe à intégrer
- *À évaluer en parallèle de l'Architecture A*

### 5.2 KYC — Contrainte sur le ticket moyen MVP
**⚠️ Alerte produit majeure :** La limite Tier 1 est de **₦20 000 par dépôt** (≈ 12–15 €). Si les transactions vêtements/chaussures dépassent ce montant, l'acheteur doit passer au Tier 2 (pièce d'identité officielle + vérification). Cela augmente la friction à l'onboarding.

**Implications :**
- Valider terrain : quel est le ticket moyen réel des transactions WhatsApp à Kano ?
- Si ticket > ₦20 000, prévoir un flux KYC Tier 2 dès le MVP
- La vérification physique d'adresse (juin 2024) est une contrainte logistique importante — qui la réalise ?

### 5.3 Structure légale — Décision nécessaire avant le MVP
- Une filiale nigériane (CAC) est probablement requise. Capital minimum : 100M NGN.
- Alternative : vérifier si une structure d'agent ou de partenariat suffit pour la phase pilote.
- Le Startup Act offre des avantages fiscaux significatifs si ≥ 33,3 % nigérian.

### 5.4 Données — Actions immédiates
- Anticiper l'enregistrement NDPC (dès 200 utilisateurs)
- Nommer ou désigner un DPO avant la collecte de données
- Mettre en place des clauses contractuelles de transfert France/Nigeria avant le lancement

### 5.5 Litiges à Kano — Implications design
- Rédiger les CGU en haoussa ET anglais (obligation légale FCCPA + confiance culturelle)
- Clause de juridiction à définir précisément pour éviter les conflits Charia/Federal
- Consulter un avocat local Kano sur la formulation du contrat Wakalah

---

## 6. Questions ouvertes — Pour avocat

*Voir le détail dans `docs/03_legal/QUESTIONS_FOR_LAWYER.md`*

Questions critiques issues de cette recherche :
1. L'Architecture Split+Disbursement (sans détention directe) est-elle reconnue par la CBN comme conforme sans licence MMO ?
2. Une lettre de non-objection CBN est-elle requise avant le lancement d'un pilote même restreint ?
3. Comment structurer la filiale nigériane CAC pour minimiser le capital social à 100M NGN ?
4. La vérification physique d'adresse Tier 1 (juin 2024) peut-elle être déléguée à un partenaire local ?
5. Quelle clause de juridiction insérer dans les CGU pour les litiges à Kano (Charia vs Common Law) ?
6. Le fondateur basé en France doit-il obtenir un CCI avant toute injection de capital, et quelle banque en est capable ?

---

## 7. Recommandations prioritaires

> Ces recommandations sont prudentes. Elles ne remplacent pas un avis d'avocat qualifié.

1. **🔴 Ne pas lancer aucune fonctionnalité de paiement** avant validation juridique de l'architecture Split+Disbursement par un avocat nigérian.
2. **🔴 Initier la recherche d'un avocat CBN fintech** immédiatement. Cabinets cités dans la recherche : Templars, Aluko & Oyebode, G. Elias.
3. **🔴 Évaluer la nécessité de la filiale CAC** avant d'intégrer des PSP ou de collecter des paiements.
4. **🟡 Anticiper le KYC Tier 1** : concevoir le produit pour les transactions ≤ ₦20 000, avec upgrade Tier 2 disponible.
5. **🟡 Engager un DPO** (même informel au départ) et préparer les clauses de transfert de données dès le design de la PWA.
6. **🟡 Consulter un expert en finance islamique** local de Kano pour valider la structure Wakalah avant de l'intégrer dans les CGU.
7. **🟢 Évaluer le Startup Act** pour bénéficier des avantages fiscaux — nécessite d'impliquer un co-fondateur ou investisseur nigérian (≥ 33,3 %).

---

## 8. Recherches complémentaires identifiées

*Ajoutées au `RESEARCH_BACKLOG.md`*

- Procédure CAC : enregistrement filiale étrangère, délais, coûts réels
- NDPC : procédure d'enregistrement, coûts, délais
- KYC Tier 1 : ticket moyen réel des transactions WhatsApp Kano (croisement avec recherche marché)
- Wakalah : jurisprudence et pratiques de finance islamique commerciale au nord Nigeria
- Non-objection letter CBN : procédure exacte et délais

---

*Fichiers mis à jour suite à cette revue : LEGAL_RISK_REGISTER.md, ESCROW_LEGAL_OPTIONS.md, QUESTIONS_FOR_LAWYER.md, PAYMENT_FLOW.md, RESEARCH_BACKLOG.md, AGENT_QUESTIONS.md, HUMAN_ACTIONS.md, DECISION_LOG.md, RESEARCH_INDEX.md*
*Mis à jour le : 2026-05-05*
