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

## Questions résolues

> *À déplacer ici depuis "Questions ouvertes" une fois tranchées, avec référence à DECISION_LOG.md*

---

*Alimenté par tous les agents dès qu'une question stratégique reste ouverte. Piloté par le CEO Orchestrator.*
