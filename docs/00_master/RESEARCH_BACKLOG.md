# RESEARCH BACKLOG — AmanaTrade

## Objectif de ce document
Centraliser tous les sujets de recherche identifiés, priorisés, et assigner leur traitement. Le Research Manager est le pilote de ce backlog.

---

## Format d'entrée

```
### [DATE] [DOMAINE] [PRIORITÉ : 🔴 Bloquant / 🟡 Important / 🟢 Utile]
**Sujet :** Ce qui doit être investigué.
**Contexte :** Pourquoi cette recherche est nécessaire.
**Questions auxquelles répondre :**
  - Question 1
  - Question 2
**Output attendu :** Fichier de destination dans docs/08_research/
**Assigné à :** Research Manager / Agent concerné
**Statut :** À faire / En cours / Terminé
```

---

## Index des recherches

| # | Domaine | Sujet | Priorité | Statut |
|---|---------|-------|----------|--------|
| R1 | Légal | Cadre CBN escrow et paiements | 🔴 Bloquant | À faire |
| R2 | Marché | WhatsApp commerce Kano | 🔴 Bloquant | À faire |
| R3 | Paiements | Comparatif APIs Nigeria | 🔴 Bloquant | À faire |
| R4 | Marché | Analyse concurrentielle Afrique de l'Ouest | 🟡 Important | À faire |
| R5 | Finance | Benchmarks modèles de revenus escrow | 🟡 Important | À faire |
| R6 | Opérations | Partenaires locaux potentiels Kano | 🟡 Important | À faire |
| R7 | Légal | Structure légale Nigeria vs étranger | 🟡 Important | À faire |
| R8 | Tech | Contraintes techniques terrain Kano | 🟢 Utile | À faire |
| R9 | Marché | Comportements paiement mobile Nord Nigeria | 🟢 Utile | À faire |
| R10 | Stratégie | Finance islamique / compatibilité sharia | 🟡 Important | À faire |
| R11 | Opérations | Politique de litige : benchmarks et terrain | 🟡 Important | À faire |

---

## Recherches prioritaires — 🔴 Bloquantes

### 2026-05-05 [LÉGAL] 🔴 — Cadre réglementaire CBN : escrow et paiements électroniques au Nigeria
**Sujet :** Légalité d'un service d'escrow opéré par une startup, licences CBN nécessaires, exigences KYC/AML, et sanctions en cas de non-conformité.
**Contexte :** Sans clarification légale, il est impossible de concevoir le flux de paiement, de choisir le partenaire PSP, ou de définir la structure juridique d'AmanaTrade. C'est le blocage le plus critique du projet.
**Questions auxquelles répondre :**
  - Quelle licence CBN est requise pour opérer un service qui détient temporairement des fonds de tiers ?
  - Une startup peut-elle sous-traiter la détention des fonds à un PSP agréé (Paystack, Flutterwave) pour éviter cette licence ?
  - Quelles sont les exigences KYC minimales pour les vendeurs et les acheteurs ?
  - Quelles sont les exigences AML (anti-money laundering) applicables ?
  - Une entreprise non nigériane peut-elle légalement opérer ce service au Nigeria ?
  - Quelles sont les pénalités en cas d'opération sans licence ?
**Output attendu :** `docs/08_research/legal/reviewed/cbn-escrow-regulation.md`
**Assigné à :** Research Manager + Legal Compliance Agent
**Statut :** À faire

---

### 2026-05-05 [MARCHÉ] 🔴 — Taille et comportement du marché WhatsApp commerce à Kano
**Sujet :** Volume de transactions informelles sur WhatsApp à Kano, segment vêtements et chaussures, comportements d'achat et de paiement.
**Contexte :** Nécessaire pour valider le TAM, la proposition de valeur, et dimensionner les objectifs de la Phase 1.
**Questions auxquelles répondre :**
  - Combien de vendeurs WhatsApp actifs existent dans le segment vêtements/chaussures à Kano ?
  - Quel est le ticket moyen d'une transaction WhatsApp dans cette catégorie ?
  - Quel est le volume mensuel estimé de transactions ?
  - Quel pourcentage de transactions aboutissent à un litige, une arnaque, ou un abandon ?
  - Quels modes de paiement sont actuellement utilisés (virement bancaire, USSD, espèces à la livraison) ?
  - Quelle est la part des acheteurs qui refusent de payer à l'avance faute de confiance ?
  - Existe-t-il des concurrents locaux ou informels qui adressent déjà ce problème ?
**Output attendu :** `docs/08_research/market/reviewed/kano-whatsapp-commerce.md`
**Assigné à :** Research Manager
**Statut :** À faire

---

### 2026-05-05 [PAIEMENTS] 🔴 — Comparatif APIs de paiement Nigeria : escrow, coûts, conformité CBN
**Sujet :** Analyse comparative des solutions de paiement disponibles au Nigeria compatibles avec un flux d'escrow.
**Contexte :** Le choix du PSP est une décision technique et financière bloquante. Il conditionne le flux de paiement, les frais de transaction, et la conformité réglementaire.
**Questions auxquelles répondre :**
  - Paystack, Flutterwave, Monnify, Squad : lesquels proposent nativement un mécanisme de hold/escrow ?
  - Quels sont les frais de transaction pour chaque solution ?
  - Lesquels supportent les virements bancaires USSD (clé pour les utilisateurs sans carte) ?
  - Quelle est la facilité d'intégration dans une PWA ?
  - Lesquels ont une conformité CBN validée pour la détention temporaire de fonds ?
  - Y a-t-il des exigences contractuelles spécifiques pour les marchands (KYB, volume minimum) ?
  - Quelle est la durée de délai de paiement vers le vendeur (settlement delay) ?
**Output attendu :** `docs/08_research/payments/reviewed/payment-apis-comparison.md`
**Assigné à :** Research Manager + Tech Architecture Agent
**Statut :** À faire

---

## Recherches importantes — 🟡

### 2026-05-05 [MARCHÉ] 🟡 — Analyse concurrentielle : solutions de confiance pour le commerce social en Afrique de l'Ouest
**Sujet :** Identifier les concurrents directs et indirects qui adressent le problème de confiance dans les transactions WhatsApp en Afrique de l'Ouest.
**Contexte :** Nécessaire pour positionner AmanaTrade et éviter de réinventer ce qui existe déjà.
**Questions auxquelles répondre :**
  - Existe-t-il des solutions d'escrow B2C au Nigeria (Grip, SafeSwap, autres) ?
  - Que font Jumia, Jiji, Konga pour la confiance acheteur-vendeur ? Pourquoi les vendeurs WhatsApp ne les utilisent-ils pas ?
  - Des solutions similaires existent-elles au Ghana, Kenya, Sénégal ? Quels enseignements tirer ?
  - Quelles sont les barrières à l'adoption de ces solutions existantes ?
**Output attendu :** `docs/08_research/market/reviewed/competitive-analysis.md`
**Assigné à :** Research Manager
**Statut :** À faire

---

### 2026-05-05 [FINANCE] 🟡 — Benchmarks de modèles économiques pour plateformes de confiance / escrow en marchés émergents
**Sujet :** Comprendre les modèles de revenus viables pour des services similaires dans des contextes comparables.
**Contexte :** La décision entre commission par transaction vs abonnement vs modèle hybride est bloquée. Des benchmarks permettront d'éclairer cette décision.
**Questions auxquelles répondre :**
  - Quel pourcentage de commission prennent les services d'escrow similaires (1 %, 2 %, 5 %) ?
  - Les vendeurs acceptent-ils un abonnement mensuel fixe ou préfèrent-ils payer à la transaction ?
  - Quels sont les seuils de ticket moyen en dessous desquels la commission n'est plus rentable ?
  - Y a-t-il des modèles freemium efficaces dans ce segment ?
**Output attendu :** `docs/08_research/finance/reviewed/revenue-model-benchmarks.md`
**Assigné à :** Research Manager + Business Finance Agent
**Statut :** À faire

---

### 2026-05-05 [OPÉRATIONS] 🟡 — Identification de partenaires locaux potentiels à Kano
**Sujet :** Identifier des organisations, ONG, associations, ou individus à Kano qui pourraient faciliter l'accès aux vendeurs WhatsApp.
**Contexte :** AmanaTrade a besoin d'un ancrage local pour les interviews terrain, le recrutement des premiers vendeurs, et la gestion des litiges physiques.
**Questions auxquelles répondre :**
  - Quelles associations de commerçants existent à Kano (Kano Chamber of Commerce, marchés centraux) ?
  - Existe-t-il des incubateurs ou programmes de soutien aux PME dans le Nord Nigeria ?
  - Des ONG ou programmes internationaux (IFC, GIZ, AFD) travaillent-ils sur le commerce digital au Nord Nigeria ?
  - Des membres de la diaspora haoussa en Europe ont-ils des connexions opérationnelles à Kano ?
**Output attendu :** `docs/08_research/market/reviewed/kano-local-partners.md`
**Assigné à :** Research Manager
**Statut :** À faire

---

### 2026-05-05 [LÉGAL] 🟡 — Structure légale pour opérer au Nigeria depuis l'étranger
**Sujet :** Options pour structurer juridiquement AmanaTrade : société française, nigériane, ou partenariat.
**Contexte :** Le fondateur est basé hors du Nigeria. La structure légale détermine les obligations fiscales, les licences accessibles, et la crédibilité locale.
**Questions auxquelles répondre :**
  - Peut-on opérer un service digital au Nigeria sans être enregistré localement ?
  - Quels sont les avantages et inconvénients d'une LLC nigériane (CAC registration) pour un fondateur étranger ?
  - Quelle est la fiscalité applicable (TVA sur services digitaux, impôts sur les revenus nigérians) ?
  - Un partenaire local peut-il porter la structure légale au Nigeria pendant la phase MVP ?
**Output attendu :** `docs/08_research/legal/reviewed/legal-structure-options.md`
**Assigné à :** Research Manager + Legal Compliance Agent
**Statut :** À faire

---

## Recherches utiles — 🟢

### 2026-05-05 [TECH] 🟢 — Accessibilité technique : smartphones, connectivité, et contraintes UX à Kano
**Sujet :** Comprendre les contraintes techniques réelles des utilisateurs cibles (modèles de téléphones, OS, connexion internet, storage) pour guider les décisions d'architecture.
**Questions auxquelles répondre :**
  - Quels sont les modèles de smartphones les plus courants à Kano ?
  - Quelle est la qualité moyenne de la connexion internet (3G, 4G, instabilités) ?
  - Quelle est la part d'utilisateurs Android vs iOS dans la cible ?
  - Les utilisateurs ont-ils l'habitude de donner des permissions à des PWA (notifications push, caméra) ?
**Output attendu :** `docs/08_research/market/reviewed/kano-tech-constraints.md`
**Assigné à :** Research Manager + Tech Architecture Agent
**Statut :** À faire

---

### 2026-05-05 [MARCHÉ] 🟢 — Comportements de paiement mobile au Nord Nigeria
**Sujet :** Comprendre l'adoption des paiements mobiles, USSD, et apps bancaires dans la population cible.
**Questions auxquelles répondre :**
  - Quel pourcentage de la population cible a un compte bancaire ?
  - Quel est le taux d'adoption de l'USSD pour les paiements ?
  - Les vendeurs WhatsApp utilisent-ils Opay, Palmpay, ou d'autres fintechs locales ?
  - Y a-t-il des résistances culturelles ou religieuses (conformité sharia) à certains types de paiement ?
**Output attendu :** `docs/08_research/payments/reviewed/north-nigeria-payment-behavior.md`
**Assigné à :** Research Manager
**Statut :** À faire

---

### 2026-05-05 [STRATÉGIE] 🟡 — Finance islamique et compatibilité sharia du modèle AmanaTrade
**Sujet :** Évaluer si le modèle de commission par transaction est compatible avec les principes de finance islamique (absence de riba), étant donné que la zone cible (Kano, Nord Nigeria) est majoritairement musulmane.
**Contexte :** Kano est une zone d'application partielle de la sharia. Certains frais de service pourraient être perçus comme assimilables à des intérêts (riba), ce qui affecterait l'adoption. À l'inverse, un positionnement comme fintech islamique pourrait être un avantage différenciant.
**Questions auxquelles répondre :**
  - La commission d'AmanaTrade est-elle considérée comme riba (interdit) ou comme ujrah (frais de service légitime) ?
  - Existe-t-il des fintechs islamiques au Nigeria avec des modèles similaires ? Comment ont-ils structuré leurs frais ?
  - Y a-t-il une résistance religieuse observable au paiement de commissions sur transactions dans la cible ?
  - Un label ou certificat de conformité sharia est-il nécessaire ou utile pour l'adoption ?
**Output attendu :** `docs/08_research/market/reviewed/sharia-compatibility.md`
**Assigné à :** Research Manager + Legal & Compliance Agent
**Statut :** À faire

---

### 2026-05-05 [OPÉRATIONS] 🟡 — Benchmarks politiques de litige pour services d'escrow en marchés émergents
**Sujet :** Analyser comment des services similaires gèrent les litiges acheteur-vendeur pour définir la politique AmanaTrade.
**Contexte :** La politique de litige est un élément clé de la proposition de valeur et de la viabilité opérationnelle. Des délais trop longs décourageront les acheteurs ; des remboursements trop faciles seront exploités par les acheteurs de mauvaise foi.
**Questions auxquelles répondre :**
  - Quels sont les délais standard de résolution de litige dans des services comparables (Escrow.com, services locaux) ?
  - Quels sont les critères de remboursement typiques (non-livraison, non-conformité) ?
  - Comment les preuves sont-elles collectées (photos, géolocalisation, témoignage) dans un contexte mobile informel ?
  - Quel est le coût opérationnel moyen d'un litige traité manuellement ?
**Output attendu :** `docs/08_research/market/reviewed/dispute-resolution-benchmarks.md`
**Assigné à :** Research Manager + Marketing & Operations Agent
**Statut :** À faire

---

## Recherches terminées
> *À déplacer ici avec la date de complétion et lien vers le fichier produit.*

---

*Alimenté par tous les agents. Piloté par le Research Manager.*
