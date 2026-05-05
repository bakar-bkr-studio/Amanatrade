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
| R1 | Légal | Cadre CBN escrow et paiements | 🔴 Bloquant | 🔄 Partiel → reviewed/ (validation avocat requise) |
| R2 | Marché | WhatsApp commerce Kano | 🔴 Bloquant | ✅ Terminé → reviewed/ |
| R3 | Paiements | Comparatif APIs Nigeria | 🔴 Bloquant | ✅ Terminé → reviewed/ |
| R4 | Marché | Analyse concurrentielle Afrique de l'Ouest | 🟡 Important | À faire |
| R16 | Marché | Volume transactions chaussures Sabon Gari (données primaires) | 🔴 Bloquant | À faire (terrain Phase 1) |
| R17 | Marché | Profil Startup Kano + Blue Sapphire Hub | 🟡 Important | À faire |
| R18 | Opérations | Partenariat Peng Logistics / Sendvoy Kano | 🟡 Important | À faire |
| R19 | Marché | Compatibilité OPay/PalmPay avec DVA NUBAN | 🔴 Bloquant | À faire (test sandbox) |
| R5 | Finance | Benchmarks modèles de revenus escrow | 🟡 Important | À faire |
| R6 | Opérations | Partenaires locaux potentiels Kano | 🟡 Important | À faire |
| R7 | Légal | Structure légale Nigeria vs étranger | 🟡 Important | À faire |
| R8 | Tech | Contraintes techniques terrain Kano | 🟢 Utile | À faire |
| R9 | Marché | Comportements paiement mobile Nord Nigeria | 🟢 Utile | À faire |
| R10 | Stratégie | Finance islamique / compatibilité sharia | 🟡 Important | À faire |
| R11 | Opérations | Politique de litige : benchmarks et terrain | 🟡 Important | À faire |
| R12 | Légal | Procédure CAC enregistrement filiale étrangère | 🔴 Bloquant | À faire |
| R13 | Données | Procédure NDPC enregistrement + DPO | 🟡 Important | À faire |
| R14 | Légal | Procédure lettre de non-objection CBN | 🔴 Bloquant | À faire |
| R15 | Légal/Finance | Wakalah jurisprudence et pratique Nord Nigeria | 🟡 Important | À faire |

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

### 2026-05-05 [PAIEMENTS] 🟡 — Conditions d'onboarding PSP pour nouvelles startups (Monnify, Squad)
**Sujet :** Comprendre les exigences contractuelles concrètes de Monnify et Squad pour intégrer une startup non encore enregistrée au Nigeria.
**Contexte :** La recherche a identifié Monnify et Squad comme PSP prioritaires, mais leurs conditions KYB (Know Your Business), volumes minimums et délais d'activation sont inconnus.
**Questions auxquelles répondre :**
  - Quelles sont les pièces justificatives requises pour s'enregistrer en tant que marchand Monnify / Squad ?
  - Y a-t-il un volume de transactions minimum ou des frais d'activation ?
  - Quel est le délai d'activation du compte sandbox → production ?
  - Une entreprise non encore enregistrée au Nigeria peut-elle accéder aux APIs ?
**Output attendu :** `docs/08_research/payments/reviewed/psp-onboarding-conditions.md`
**Assigné à :** Research Manager + Tech Architecture Agent
**Statut :** À faire

---

### 2026-05-05 [PAIEMENTS] 🟡 — Taux d'échec et délais réels des transactions NIBSS à Kano
**Sujet :** Mesurer les taux d'échec, de timeout et de retard de réconciliation NIBSS dans des conditions réelles à Kano, pour dimensionner l'UX de tolérance aux erreurs.
**Contexte :** Le rapport de recherche signale que les retards NIBSS peuvent impacter l'UX. Les données disponibles sont des moyennes nationales, pas des données Kano spécifiques ni en heures de pointe.
**Questions auxquelles répondre :**
  - Quel est le taux d'échec moyen des virements interbancaires NIBSS au Nigeria ?
  - Des données existent-elles pour Kano ou le Nord Nigeria spécifiquement ?
  - Comment les PSP (Monnify, Paystack) gèrent-ils les fonds en attente en cas de timeout NIBSS ?
  - Quel SLA les PSP offrent-ils sur la confirmation des Webhooks ?
**Output attendu :** `docs/08_research/payments/reviewed/nibss-failure-rates.md`
**Assigné à :** Research Manager
**Statut :** À faire

---

---

### 2026-05-05 [LÉGAL] 🔴 — Procédure CAC : enregistrement d'une filiale étrangère au Nigeria
**Sujet :** Étapes concrètes, documents requis, délais et coûts pour enregistrer une filiale nigériane (LLC) auprès de la Corporate Affairs Commission (CAC).
**Contexte :** La loi CAMA 2020 impose cet enregistrement. Sans filiale, AmanaTrade ne peut pas légalement opérer, ni ouvrir de compte bancaire nigérian, ni signer de contrats PSP.
**Questions auxquelles répondre :**
  - Quelles sont les étapes exactes d'enregistrement CAC pour une société à participation étrangère ?
  - Le capital nominal de 100 M NGN doit-il être déposé en totalité dès le départ ?
  - Quel est le délai réaliste d'enregistrement (semaines ? mois ?) ?
  - Quels sont les coûts réels (honoraires avocat, droits d'enregistrement, droits de timbre 0,75 %) ?
  - Un directeur résident nigérian est-il obligatoire, et comment l'identifier ?
**Output attendu :** `docs/08_research/legal/reviewed/cac-registration-procedure.md`
**Assigné à :** Research Manager + Legal Compliance Agent
**Statut :** À faire

---

### 2026-05-05 [DONNÉES] 🟡 — Procédure NDPC enregistrement et DPO
**Sujet :** Étapes d'enregistrement auprès de la Commission de Protection des Données du Nigeria (NDPC), désignation d'un DPO, et audit annuel via DPCO.
**Contexte :** Obligation légale dès 200 utilisateurs sous NDPA 2023.
**Questions auxquelles répondre :**
  - Quelle est la procédure d'enregistrement NDPC ? Délais et coûts ?
  - Un DPO externe est-il accepté, et quel est son coût estimé au Nigeria ?
  - Quelles sont les DPCO certifiées opérant au Nigeria ?
  - Quels documents sont requis pour l'audit annuel ?
**Output attendu :** `docs/08_research/legal/reviewed/ndpc-registration-dpo.md`
**Assigné à :** Research Manager
**Statut :** À faire

---

### 2026-05-05 [LÉGAL] 🔴 — Procédure de la lettre de non-objection CBN
**Sujet :** Comprendre la procédure exacte pour obtenir une "lettre de non-objection" (no-objection letter) de la CBN avant de lancer un service fintech en partenariat avec un PSP licencié.
**Contexte :** La CBN exige cette lettre. Son absence peut entraîner la fermeture forcée d'AmanaTrade.
**Questions auxquelles répondre :**
  - Quels documents sont requis pour faire la demande ?
  - Quel est le délai réaliste d'obtention ?
  - Cette lettre est-elle requise pour une phase pilote non-commerciale ?
  - Des cabinets d'avocat ont-ils une expérience documentée dans l'obtention de ces lettres ?
**Output attendu :** `docs/08_research/legal/reviewed/cbn-no-objection-procedure.md`
**Assigné à :** Research Manager + Legal Compliance Agent
**Statut :** À faire

---

### 2026-05-05 [LÉGAL/STRATÉGIE] 🟡 — Wakalah : jurisprudence et pratique dans le commerce au Nord Nigeria
**Sujet :** Évaluer la solidité juridique et l'acceptation culturelle du modèle contractuel Wakalah dans le contexte commercial de Kano.
**Contexte :** Le modèle Wakalah est identifié comme un outil de conformité sharia et de différenciation. Mais son applicabilité devant les tribunaux nigérians et son acceptation réelle par les commerçants haoussa n'ont pas été validées.
**Questions auxquelles répondre :**
  - Existe-t-il une jurisprudence nigériane récente (tribunaux Charia ou civils) reconnaissant les contrats Wakalah dans le commerce électronique ?
  - Les commerçants haoussa de Kano sont-ils familiers du concept Wakalah, ou est-ce un terme perçu comme purement théorique ?
  - Quels sont les éléments contractuels essentiels d'un Wakalah valide selon le droit islamique nigérian ?
  - Y a-t-il un scholar islamique ou un cabinet d'avocat spécialisé finance islamique à Kano ou Abuja pouvant valider le contrat ?
**Output attendu :** `docs/08_research/legal/reviewed/wakalah-nigeria-practice.md`
**Assigné à :** Research Manager + Legal Compliance Agent
**Statut :** À faire

---

---

### 2026-05-05 [MARCHÉ] 🔴 — Volume mensuel de transactions chaussures à Sabon Gari (données primaires)
**Sujet :** Estimer le volume de transactions mensuelles dans le segment chaussures au marché Sabon Gari de Kano — données manquantes dans la recherche documentaire.
**Contexte :** La recherche documentaire n'a pas permis d'obtenir des données de volume spécifiques à Sabon Gari. Cette donnée est nécessaire pour dimensionner le TAM et valider la viabilité du pilote.
**Questions auxquelles répondre :**
  - Combien de vendeurs de chaussures sont actifs sur WhatsApp à Sabon Gari ?
  - Quel est le volume mensuel estimé de transactions chaussures (informel et formel) ?
  - Quel pourcentage de ces transactions se font via WhatsApp vs en boutique physique ?
**Output attendu :** `docs/08_research/market/reviewed/sabon-gari-shoe-market-volume.md`
**Assigné à :** Research Manager — données primaires terrain Phase 1
**Statut :** À faire (données primaires requises)

---

### 2026-05-05 [MARCHÉ] 🟡 — Profil détaillé Startup Kano et Blue Sapphire Hub (partenaires potentiels)
**Sujet :** Comprendre les programmes, contacts, et accès aux vendeurs de Startup Kano et Blue Sapphire Hub pour le recrutement des vendeurs champions.
**Contexte :** Ces deux hubs sont identifiés comme canaux de recrutement prioritaires pour le pilote. Mais leur accès aux vendeurs de marché (Sabon Gari) vs aux tech startups n'est pas encore clair.
**Questions auxquelles répondre :**
  - Startup Kano et Blue Sapphire Hub travaillent-ils avec des vendeurs WhatsApp de marché, ou uniquement avec des fondateurs tech ?
  - Quels sont les contacts clés ? Y a-t-il des événements, programmes ou canaux WhatsApp ?
  - Ont-ils une communauté de vendeurs e-commerce / social commerce ?
**Output attendu :** `docs/08_research/market/reviewed/kano-local-partners.md`
**Assigné à :** Research Manager + Marketing Operations Agent
**Statut :** À faire

---

### 2026-05-05 [OPÉRATIONS] 🟡 — Conditions de partenariat Peng Logistics et Sendvoy à Kano
**Sujet :** Évaluer la possibilité d'un partenariat logistique avec Peng Logistics et/ou Sendvoy pour la livraison + vérification physique à la livraison lors du pilote Phase 1.
**Contexte :** Ces deux opérateurs sont identifiés dans la recherche comme actifs au Nigeria et utilisant WhatsApp. Leur présence à Kano, leurs tarifs, et leur capacité à jouer un rôle de vérificateur sont inconnus.
**Questions auxquelles répondre :**
  - Peng Logistics opère-t-il à Kano (pas seulement Lagos/Abuja) ?
  - Quels sont les délais et tarifs de livraison last-mile Sabon Gari → zone universitaire Kano ?
  - Peuvent-ils jouer un rôle de "vérificateur" à la livraison (confirmation de conformité de l'article) ?
  - Conditions d'un partenariat commercial avec une startup en Phase 1 ?
**Output attendu :** `docs/08_research/market/reviewed/kano-logistics-partners.md`
**Assigné à :** Research Manager + Marketing Operations Agent
**Statut :** À faire

---

### 2026-05-05 [MARCHÉ] 🟡 — Adoption OPay / PalmPay à Kano : compatibilité DVA NUBAN
**Sujet :** Valider si un utilisateur d'OPay ou PalmPay peut effectuer un virement vers un DVA NUBAN Monnify/Squad, et si ce virement déclenche correctement le Webhook.
**Contexte :** OPay et PalmPay sont les wallets dominants à Kano. Si les acheteurs utilisant ces wallets ne peuvent pas payer via le DVA, une partie significative de la cible est exclue du flux de paiement MVP.
**Questions auxquelles répondre :**
  - OPay permet-il les virements sortants vers des NUBAN externes (hors réseau OPay) ?
  - PalmPay permet-il les virements sortants vers des NUBAN Monnify/Squad ?
  - Un test sandbox peut-il simuler ce flux ?
  - Faut-il intégrer une API unifiée (ex: Korapay) pour accéder aux wallets OPay/PalmPay ?
**Output attendu :** `docs/08_research/payments/reviewed/north-nigeria-payment-behavior.md`
**Assigné à :** Research Manager + Tech Architecture Agent
**Statut :** À faire — test sandbox requis

---

## Recherches terminées

### 2026-05-05 [MARCHÉ] ✅ — Taille et comportement du marché WhatsApp commerce à Kano
**Complété le :** 2026-05-05
**Fichier produit :** `docs/08_research/market/reviewed/2026-05-05_kano-whatsapp-commerce-review.md`
**Résumé des conclusions :** WhatsApp = OS commercial complet à Kano. Kantin Kwari 90 % contrefaçons. Sabon Gari = hub préféré pour le pilote (vendeurs plus tech-savvy, articles à valeur élevée). AOV vêtements ~₦17 500, chaussures ₦35 000–60 000 (> plafond KYC Tier 1 ₦20k — tension critique). Commission 2,5–3 % validée comme hypothèse. Concept Amana = avantage culturel profond. Startup Kano + Blue Sapphire Hub = recrutement vendeurs. Peng Logistics + Sendvoy = partenaires logistiques potentiels. Modèle concierge recommandé pour les premières transactions.

---

### 2026-05-05 [LÉGAL] 🔄 Partiel — Cadre réglementaire nigérian : escrow, paiements, données, structure légale
**Complété le :** 2026-05-05 (recherche documentaire — validation avocat non encore réalisée)
**Fichier produit :** `docs/08_research/legal/reviewed/2026-05-05_nigeria-escrow-regulation-review.md`
**Résumé des conclusions :** MMO seul peut détenir des fonds (2 Md NGN capital). Architecture Split+Disbursement = hypothèse légale viable non encore validée. KYC Tier 1 limité à ₦20 000/transaction. Filiale CAC probablement requise (100 M NGN). Lettre de non-objection CBN requise. NDPA 2023 impose DPO + enregistrement NDPC + audit annuel. Trust Account bancaire = alternative à évaluer.

### 2026-05-05 [PAIEMENTS] ✅ — Comparatif APIs de paiement Nigeria : escrow, coûts, conformité CBN
**Complété le :** 2026-05-05
**Fichier produit :** `docs/08_research/payments/reviewed/2026-05-05_nigeria-payment-providers-review.md`
**Résumé des conclusions :** Monnify et Squad identifiés comme PSP prioritaires. Architecture Hold & Release via Split+Disbursement API identifiée comme alternative légale à l'escrow direct. BVN/NIN obligatoires Tier 1. Cartes bancaires à exclure du MVP. Web Share API pour intégration WhatsApp.

---

*Alimenté par tous les agents. Piloté par le Research Manager.*

