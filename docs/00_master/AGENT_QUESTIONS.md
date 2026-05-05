# AGENT QUESTIONS — AmanaTrade

## Objectif de ce document
Centraliser toutes les questions ouvertes identifiées par les agents. Ces questions nécessitent soit une décision du fondateur, soit une recherche approfondie, soit une consultation externe (avocat, expert local, etc.).

---

## Format d'entrée

```
### [DATE] [AGENT] [PRIORITÉ : 🔴 Bloquant / 🟡 Important / 🟢 À traiter]
**Question :** La question précise.
**Contexte :** Pourquoi cette question est ouverte.
**Impact si non résolue :** Ce qui reste bloqué.
**Piste de résolution :** Recherche / Décision fondateur / Consultation avocat / Autre.
**Statut :** Ouvert / En cours / Résolu → voir DECISION_LOG.md
```

---

## Questions ouvertes

### 2026-05-05 [CEO Orchestrator] 🔴 — Le service d'escrow d'AmanaTrade est-il légalement opérable au Nigeria sans licence CBN ?
**Question :** AmanaTrade peut-il légalement détenir des fonds de tiers entre un acheteur et un vendeur, même temporairement, sans avoir la licence de Payment Service Provider délivrée par la CBN ?
**Contexte :** Le modèle d'escrow implique qu'AmanaTrade retient le paiement de l'acheteur jusqu'à confirmation de livraison avant de le transférer au vendeur. Cela pourrait constituer une activité de détention de fonds réglementée par la CBN.
**Impact si non résolue :** Bloque entièrement la conception du flux de paiement, le choix du PSP, le modèle économique, et la structure légale. Sans réponse, on ne peut pas construire le produit.
**Piste de résolution :** Consultation d'un avocat nigérian spécialisé en fintech + lecture des circulaires CBN sur les Payment Service Providers. Voir `docs/03_legal/QUESTIONS_FOR_LAWYER.md`.
**Statut :** Ouvert

---

### 2026-05-05 [CEO Orchestrator] 🔴 — Quel est le modèle de revenus optimal pour AmanaTrade dans le contexte du marché de Kano ?
**Question :** AmanaTrade doit-il facturer une commission par transaction (% du montant), un abonnement mensuel fixe aux vendeurs, ou un modèle hybride ? À quel niveau de prix ?
**Contexte :** Cette décision impacte directement la proposition de valeur aux vendeurs, la viabilité économique, et la conception de l'interface (affichage des frais). Les benchmarks comparatifs manquent encore et les interviews terrain n'ont pas encore eu lieu.
**Impact si non résolue :** Bloque les projections financières, la finalisation du PRD, et le discours d'acquisition des vendeurs.
**Piste de résolution :** (1) Benchmarks de modèles économiques concurrents — voir RESEARCH_BACKLOG.md. (2) Test de sensibilité au prix lors des interviews vendeurs Phase 1. (3) Décision finale par le fondateur.
**Statut :** Ouvert

---

### 2026-05-05 [CEO Orchestrator] 🔴 — Quel PSP utiliser pour gérer les paiements et le mécanisme de hold/escrow ?
**Question :** Parmi Paystack, Flutterwave, Monnify, Squad, et d'autres, lequel offre le mécanisme de hold/release de fonds le plus adapté au flux AmanaTrade, avec la conformité CBN requise et des coûts acceptables dans le budget 10 000 € ?
**Contexte :** La réponse dépend à la fois de la recherche technique sur les APIs et de la clarification légale (certains PSP peuvent lever le besoin de licence CBN directe s'ils portent eux-mêmes la détention de fonds).
**Impact si non résolue :** Bloque TECH_ARCHITECTURE.md, PAYMENT_FLOW.md, et DEVELOPMENT_HANDOFF.md.
**Piste de résolution :** Comparatif APIs de paiement — voir RESEARCH_BACKLOG.md. Coordonner avec le résultat de la question légale CBN.
**Statut :** Ouvert

---

### 2026-05-05 [CEO Orchestrator] 🟡 — Quelle structure légale adopter pour opérer AmanaTrade depuis l'étranger ?
**Question :** Le fondateur étant basé hors du Nigeria, quelle est la structure légale optimale : société nigériane (CAC), société française avec filiale nigériane, ou partenariat avec une entité locale ?
**Contexte :** La structure légale impacte les obligations fiscales, les licences accessibles, la crédibilité locale auprès des vendeurs, et la capacité à lever des fonds locaux.
**Impact si non résolue :** Peut bloquer l'ouverture d'un compte bancaire nigérian, la signature de contrats PSP, et les futurs partenariats institutionnels.
**Piste de résolution :** Consultation avocat nigérian. Recherche complémentaire sur les options — voir RESEARCH_BACKLOG.md (`legal-structure-options.md`).
**Statut :** Ouvert

---

### 2026-05-05 [CEO Orchestrator] 🟡 — L'interface haoussa est-elle un avantage différenciateur suffisant pour l'adoption, ou faut-il autre chose ?
**Question :** Les vendeurs WhatsApp à Kano choisiraient-ils AmanaTrade principalement parce que l'interface est en haoussa, ou d'autres facteurs (confiance de la marque, simplicité, coût, vitesse) sont-ils plus déterminants ?
**Contexte :** La décision langue haoussa-first a été actée mais n'a pas encore été validée terrain. Si la langue n'est pas le facteur principal d'adoption, les ressources de traduction et localisation pourraient être redéployées ailleurs.
**Impact si non résolue :** Risque de sur-investir dans la localisation haoussa si ce n'est pas le facteur d'adoption principal. Ou risque inverse : sous-estimer son importance.
**Piste de résolution :** Question à inclure dans le guide d'entretien des interviews vendeurs Phase 1. Décision fondateur après résultats.
**Statut :** Ouvert

---

### 2026-05-05 [CEO Orchestrator] 🟡 — Y a-t-il des contraintes culturelles ou religieuses (finance islamique, sharia) à intégrer dans le modèle de paiement ?
**Question :** Une partie significative de la population cible à Kano (Nord Nigeria, zone majoritairement musulmane) applique-t-elle des principes de finance islamique ? Si oui, des mécanismes comme les intérêts de retard ou certains types de frais seraient-ils problématiques ?
**Contexte :** Kano est dans une zone à forte majorité musulmane avec application partielle de la sharia. Certains produits financiers peuvent être perçus comme incompatibles avec les principes islamiques (riba = intérêts). Cela pourrait affecter la conception des frais de service.
**Impact si non résolue :** Risque de rejeter une partie de la cible si le modèle de revenus est perçu comme non-conforme. Ou opportunité de se positionner comme "fintech islamique".
**Piste de résolution :** Question à inclure dans les interviews terrain. Recherche sur la finance islamique au Nord Nigeria.
**Statut :** Ouvert

---

### 2026-05-05 [CEO Orchestrator] 🟡 — Quel est le budget minimal réaliste pour atteindre la fin de la Phase 1 (validation terrain) ?
**Question :** Le budget alloué à la Phase 1 (interviews terrain, partenaire local, conseil juridique) est-il réaliste avec moins de 2 000 € ? Ou faut-il revoir le plafond de 10 000 € pour tenir compte du coût réel d'un avocat nigérian et d'un relais terrain ?
**Contexte :** Les coûts d'un avocat spécialisé CBN au Nigeria sont inconnus. Les frais de déplacement, de traduction, et d'un relais terrain sont également des inconnues. Sans estimation réaliste, le budget de Phase 1 est une hypothèse non fondée.
**Impact si non résolue :** Risque de sous-budgéter la Phase 1 et de devoir l'interrompre faute de fonds, compromettant la validation terrain.
**Piste de résolution :** (1) Demander des devis à 2–3 avocats nigérians fintech via LinkedIn ou Lawpadi. (2) Estimer les coûts d'un relais terrain Kano. (3) Réviser STARTUP_BUDGET.md avec des fourchettes réalistes.
**Statut :** Ouvert

---

### 2026-05-05 [Tech Architecture + Legal] 🔴 — L'architecture Split + Disbursement via PSP licencié est-elle légalement conforme CBN sans licence propre ?
**Question :** L'utilisation des APIs de Split Payment et de Disbursement de Monnify ou Squad pour simuler un escrow (fonds retenus dans l'environnement du PSP, libérés sur confirmation de réception) constitue-t-elle une activité licenciée par la CBN — ou est-elle légalement assimilable à un simple service d'orchestration sans détention de fonds ?
**Contexte :** La recherche identifie cette architecture comme l'alternative légale à l'escrow direct, mais cette conclusion n'a pas été validée par un avocat nigérian. C'est l'hypothèse la plus critique du projet : si elle est fausse, tout le modèle technique doit être revu.
**Impact si non résolue :** Bloque la finalisation de PAYMENT_FLOW.md, TECH_ARCHITECTURE.md, le PRD, et la recherche de développeur. C'est le blocage n°1 technique et légal.
**Piste de résolution :** Consultation avocat nigérian fintech/CBN avec un brief technique précis sur l'architecture Split+Disbursement. Transmettre `docs/03_legal/QUESTIONS_FOR_LAWYER.md` enrichi de cette question.
**Statut :** Ouvert

---

### 2026-05-05 [Legal + Product] 🔴 — Le positionnement contractuel Wakalah est-il juridiquement valide et reconnu au Nigeria ?
**Question :** Peut-on structurer les Conditions Générales d'Utilisation d'AmanaTrade autour du concept islamique de *Wakalah* (agence mandatée) pour justifier la commission de service comme *ujrah* (honoraires légitimes) et éviter toute assimilation à du *riba* (intérêts) ? Ce cadre contractuel est-il reconnu par les tribunaux nigérians et les autorités religieuses de Kano ?
**Contexte :** La recherche identifie le Wakalah comme une opportunité de différenciation et de conformité sharia dans le marché de Kano. Mais ce n'est qu'un cadre théorique sans validation juridique ou terrain.
**Impact si non résolue :** Si le positionnement Wakalah est contesté, AmanaTrade perd un avantage concurrentiel majeur dans le Nord Nigeria. À l'inverse, s'il n'est pas validé et qu'AmanaTrade le communique publiquement, cela peut entraîner une perte de confiance.
**Piste de résolution :** (1) Consultation d'un avocat nigérian avec expertise en finance islamique. (2) Entretien avec un érudit religieux (scholar) haoussa. (3) Inclure la question dans les interviews terrain Phase 1.
**Statut :** Ouvert

---

### 2026-05-05 [Tech Architecture] 🟡 — OPay et PalmPay sont-ils compatibles en entrée avec les DVA NUBAN de Monnify et Squad ?
**Question :** Un utilisateur d'OPay ou PalmPay peut-il effectuer un virement vers un compte virtuel NUBAN généré par Monnify ou Squad, et ce virement déclenche-t-il correctement le Webhook de confirmation ? Ou ces wallets ferment-ils les transferts sortants aux seuls NUBAN de leur propre réseau ?
**Contexte :** OPay et PalmPay sont les wallets mobiles dominants à Kano. Si un acheteur ne peut pas payer depuis OPay vers le DVA AmanaTrade (Monnify/Squad), une part majeure de la cible est exclue du flux de paiement.
**Impact si non résolue :** Risque de devoir reconfigurer l'architecture de paiement pour ajouter Korapay (API unifiée OPay/PalmPay). Décision tech bloquante avant MVP.
**Piste de résolution :** Test technique en sandbox Monnify/Squad : tenter un virement depuis un compte OPay test vers un DVA NUBAN. Consulter la documentation ou le support technique de Monnify.
**Statut :** Ouvert

---

### 2026-05-05 [Legal + CEO Orchestrator] 🔴 — AmanaTrade doit-il créer une filiale nigériane (CAC) avant de recruter des utilisateurs ?
**Question :** La loi CAMA 2020 exige qu'une société étrangère crée une filiale locale enregistrée auprès de la CAC pour opérer au Nigeria. Cette obligation s'applique-t-elle dès la phase pilote (< 50 vendeurs) ou uniquement lors d'une activité commerciale à pleine échelle ? Si oui, avec quel capital social réel (pas uniquement les 100 M NGN nominaux) et dans quel délai ?
**Contexte :** Le fondateur est basé en France. Si la filiale CAC est un prérequis absolu, cela ajoute un coût et un délai non budgétés en Phase 0.
**Impact si non résolue :** Risque légal majeur si on recrute des utilisateurs sans structure locale. Bloque également l'accès aux licences CBN et aux comptes bancaires nigérians.
**Piste de résolution :** Consultation avocat nigérian — question prioritaire dans `QUESTIONS_FOR_LAWYER.md`.
**Statut :** Ouvert

---

### 2026-05-05 [Legal + Product] 🔴 — La vérification physique d'adresse KYC Tier 1 (juin 2024) — qui la réalise dans le contexte AmanaTrade ?
**Question :** La mise à jour CBN de juin 2024 exige une vérification physique de l'adresse même pour les comptes de niveau Tier 1. Comment cette obligation peut-elle être remplie par AmanaTrade (opération à distance, pas de présence physique initiale à Kano) ? Peut-on déléguer cette vérification au PSP partenaire ?
**Contexte :** Si AmanaTrade doit vérifier physiquement l'adresse de chaque vendeur, l'onboarding à distance est impossible sans relais local. Cela impacte directement la stratégie go-to-market et le coût d'acquisition.
**Impact si non résolue :** Bloque le design du flux d'onboarding. Peut nécessiter des agents terrain dès le MVP.
**Piste de résolution :** Consultation avocat + question explicite à Monnify/Squad : est-ce que leur KYC API couvre la vérification physique d'adresse ?
**Statut :** Ouvert

---

### 2026-05-05 [Legal + CEO Orchestrator] 🟡 — Le modèle Trust Account (Option E) est-il légalement plus solide que le Split+Disbursement (Option B) ?
**Question :** La recherche identifie deux architectures viables : (B) Split+Disbursement via PSP et (E) Trust Account / compte fiduciaire bancaire. L'Option E, où les fonds sont dans un compte bancaire fiduciaire formel, offre-t-elle une protection légale supérieure face à la réglementation CBN ? Le surcroît de complexité est-il justifié pour le MVP ?
**Contexte :** L'Option B est plus facile à intégrer techniquement. L'Option E est potentiellement plus robuste légalement. La réponse conditionne des mois de développement.
**Impact si non résolue :** Peut obliger à refaire l'architecture technique si l'Option B est rejetée par l'avocat.
**Piste de résolution :** Question explicite à l'avocat nigérian. Documenter les deux options dans `ESCROW_LEGAL_OPTIONS.md`.
**Statut :** Ouvert

---

### 2026-05-05 [Legal + Finance] 🟡 — Le fondateur doit-il intégrer un co-fondateur ou investisseur nigérian pour bénéficier du Nigeria Startup Act ?
**Question :** Le Nigeria Startup Act 2022 offre 4 ans d'exonération fiscale et un accès facilité aux licences, mais exige ≥ 33,3 % du capital détenu par des Nigérians. Est-ce une priorité à anticiper dès la création de la filiale CAC, ou peut-on l'ignorer en Phase 0–1 et l'envisager en Phase 2 si les ressources le permettent ?
**Contexte :** Intégrer un co-fondateur ou investisseur nigérian pour remplir la condition des 33,3 % peut être stratégiquement utile (réseau local, crédibilité) mais aussi risqué (gouvernance, dilution).
**Impact si non résolue :** Si la filiale CAC est créée sans respecter la condition, obtenir le Startup Label rétroactivement peut être complexe.
**Piste de résolution :** Consultation avocat + Business & Finance Agent (analyse de la dilution).
**Statut :** Ouvert

---

## Questions résolues

> *À déplacer ici depuis "Questions ouvertes" une fois tranchées, avec référence à DECISION_LOG.md*

---

*Alimenté par tous les agents dès qu'une question stratégique reste ouverte. Piloté par le CEO Orchestrator.*
