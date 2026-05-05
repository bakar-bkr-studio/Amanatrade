# DECISION LOG — AmanaTrade

## Objectif de ce document
Tracer toutes les décisions structurantes du projet : ce qui a été décidé, pourquoi, par qui, et quand. Ce log est la mémoire décisionnelle du projet.

---

## Format d'entrée

```
### [DATE] [DOMAINE] — Titre de la décision
**Décision :** Ce qui a été décidé.
**Contexte :** Pourquoi cette décision était nécessaire.
**Alternatives considérées :** Options écartées et raisons.
**Décidé par :** Fondateur / Agent concerné.
**Impact :** Fichiers ou plans affectés.
**Réversibilité :** Facilement réversible / Difficile à revenir en arrière.
```

---

## Décisions actées

### 2026-05-05 [GLOBAL] — Création du QG stratégique séparé du code applicatif
**Décision :** Le repo `amanatrade-hq` est dédié uniquement aux documents stratégiques. Aucun code applicatif ne sera écrit ici.
**Contexte :** Besoin d'un espace centralisé, versionnable, pour structurer la réflexion avant de développer quoi que ce soit. Séparer la stratégie du code permet de garder chaque repo focalisé.
**Alternatives considérées :** Tout mettre dans des Google Docs — écarté (moins structuré, moins versionnable, moins compatible avec l'usage d'agents IA).
**Décidé par :** Fondateur.
**Impact :** Création de la structure `amanatrade-hq/`. Le futur repo applicatif sera distinct.
**Réversibilité :** Facilement réversible.

---

### 2026-05-05 [STRATÉGIE] — Géographie initiale : Kano
**Décision :** Le lancement du MVP se fera exclusivement à Kano.
**Contexte :** Kano est la deuxième plus grande ville du Nigeria et la capitale économique et commerciale du Nord. Elle concentre une forte densité de vendeurs informels et un usage WhatsApp intensif dans le commerce. Démarrer à Kano permet de valider le modèle dans un contexte représentatif sans diluer les ressources.
**Alternatives considérées :**
- Abuja — écarté (marché plus formel, moins représentatif du commerce social haoussa)
- Lagos — écarté (trop concurrentiel, hors cible culturelle et linguistique)
- Plusieurs villes en parallèle — écarté (budget insuffisant, risque de dispersion)
**Décidé par :** Fondateur.
**Impact :** MASTER_PLAN.md, MVP_SCOPE.md, GO_TO_MARKET.md, FIELD_TEST_PLAN.md.
**Réversibilité :** Facilement réversible (l'expansion Phase 4 prévoit d'autres villes).

---

### 2026-05-05 [PRODUIT] — Cible utilisateurs : vendeurs WhatsApp professionnels + acheteurs particuliers
**Décision :** Les utilisateurs primaires sont des vendeurs qui utilisent déjà WhatsApp comme canal de vente principal, et des acheteurs particuliers qui achètent via ces mêmes vendeurs. Le service n'est pas B2B (pas pour des boutiques physiques avec ERP) ni grand public généraliste.
**Contexte :** Ces vendeurs n'ont pas accès à des solutions de paiement sécurisé fiables. La confiance est le problème central. Un acheteur qui ne connaît pas le vendeur hésite à payer à l'avance ; un vendeur ne veut pas livrer sans paiement. AmanaTrade résout ce point de friction précis.
**Alternatives considérées :**
- Boutiques physiques — écarté (besoin différent, déjà mieux servi)
- Grandes plateformes de e-commerce — écarté (hors portée MVP, complexité supérieure)
**Décidé par :** Fondateur.
**Impact :** PRD.md, USER_JOURNEYS.md, GO_TO_MARKET.md, DESIGN_BRIEF.md.
**Réversibilité :** Réversible mais coûteux (implique un redesign du flux produit).

---

### 2026-05-05 [PRODUIT] — Catégories MVP : vêtements et chaussures uniquement
**Décision :** La version MVP se limite aux transactions portant sur des vêtements et des chaussures.
**Contexte :** Ces catégories représentent un volume de transactions informelles très élevé dans le Nord Nigeria. Elles impliquent des tickets moyens modestes (idéal pour tester la confiance) et sont tangibles (livraison physique, inspection possible). Limiter les catégories permet de contrôler les cas d'usage, les litiges potentiels, et la politique de remboursement.
**Alternatives considérées :**
- Téléphones et électronique — écarté (tickets plus élevés, fraude plus complexe, litiges plus difficiles)
- Toutes catégories — écarté (trop large pour un MVP, politique de litige impossible à gérer)
- Alimentation — écarté (périssable, logistique incompatible)
**Décidé par :** Fondateur.
**Impact :** MVP_SCOPE.md, DISPUTE_RESOLUTION_POLICY.md, PRD.md.
**Réversibilité :** Facilement extensible en Phase 3.

---

### 2026-05-05 [TECH] — Format produit : PWA mobile-first
**Décision :** AmanaTrade sera développé sous forme de Progressive Web App (PWA), optimisée pour mobile.
**Contexte :** Les utilisateurs cibles (vendeurs et acheteurs à Kano) utilisent des smartphones Android d'entrée de gamme avec des connexions internet parfois instables. Une PWA évite les frictions d'installation d'une app native, permet un accès via lien WhatsApp direct, et réduit le coût et la complexité de développement initial.
**Alternatives considérées :**
- App native Android — écarté (délai de développement plus long, pas de iOS, frais Play Store)
- App native iOS + Android — écarté (coût prohibitif pour le budget disponible)
- Site web classique non-PWA — écarté (moins adapté au mobile, pas de mode offline partiel)
**Décidé par :** Fondateur.
**Impact :** TECH_ARCHITECTURE.md, DEVELOPMENT_HANDOFF.md, DESIGN_BRIEF.md.
**Réversibilité :** Une PWA peut évoluer vers une app native plus tard. Peu risqué.

---

### 2026-05-05 [PRODUIT] — Langue principale : haoussa, anglais second
**Décision :** L'interface et les communications utilisateur seront en haoussa en priorité, avec l'anglais en support.
**Contexte :** La grande majorité des vendeurs et acheteurs cibles à Kano sont des locuteurs natifs haoussa. Une interface en haoussa est un avantage concurrentiel direct et un signal fort de confiance culturelle. L'anglais reste nécessaire pour les utilisateurs bilingues et pour la documentation technique.
**Alternatives considérées :**
- Anglais uniquement — écarté (exclurait une grande partie de la cible, friction d'adoption)
- Anglais + pidgin — écarté (pidgin moins courant au Nord qu'au Sud Nigeria)
**Décidé par :** Fondateur.
**Impact :** DESIGN_BRIEF.md, PRD.md, GO_TO_MARKET.md.
**Réversibilité :** Facilement extensible (ajout d'autres langues en Phase 3).
**Hypothèse à valider** : Vérifier lors des interviews terrain que les vendeurs préfèrent effectivement une interface haoussa vs anglaise.

---

### 2026-05-05 [FINANCE] — Budget personnel maximum : 10 000 €
**Décision :** Le fondateur s'engage à ne pas dépenser plus de 10 000 € de fonds personnels sur ce projet avant d'avoir obtenu un financement externe ou prouvé le modèle.
**Contexte :** Contrainte de capital réelle. Permet de forcer la discipline : chaque dépense doit être justifiée par une validation de marché ou une nécessité opérationnelle. Évite de sur-investir dans un concept non validé.
**Alternatives considérées :**
- Lever des fonds dès la Phase 0 — écarté (trop tôt, pas encore de traction ni de validation)
- Pas de plafond défini — écarté (risque de dérive des coûts)
**Décidé par :** Fondateur.
**Impact :** STARTUP_BUDGET.md, FINANCIAL_MODEL.md, FUNDING_OPTIONS_ANALYSIS.md, MASTER_PLAN.md.
**Réversibilité :** Révisable si un financement externe est obtenu.

---

### 2026-05-05 [TECH/PRODUIT] — Exclusion des cartes bancaires du flux de paiement MVP
**Décision :** Les cartes bancaires (Mastercard, Visa, Verve) sont exclues du flux de paiement du MVP AmanaTrade.
**Contexte :** La recherche de paiements confirme que les cartes bancaires sont massivement rejetées par les acheteurs particuliers pour les petites transactions de commerce social, en raison de la méfiance vis-à-vis de la saisie de numéros de carte sur des liens inconnus et des frictions liées à l'authentification forte (3D Secure, OTP). L'imposer nuirait directement au taux de conversion.
**Alternatives considérées :**
- Cartes bancaires incluses — écarté (friction élevée, taux d'adoption faible dans la cible Kano)
**Décidé par :** CEO Orchestrator sur la base de la recherche (source : `docs/08_research/payments/reviewed/2026-05-05_nigeria-payment-providers-review.md`).
**Impact :** PAYMENT_FLOW.md, MVP_SCOPE.md, DESIGN_BRIEF.md.
**Réversibilité :** Facilement réversible en Phase 3 si la cible évolue.

---

### 2026-05-05 [STRATÉGIE] — Territoire prioritaire intra-Kano : Sabon Gari (vs Kantin Kwari)
**Décision :** Le pilote Phase 1 se concentrera sur le marché Sabon Gari (Muhammad Abubakar Rimi Market), et non sur Kantin Kwari.
**Contexte :** La recherche documentaire confirme que Kantin Kwari est dominé par les contrefaçons (90 % des textiles) et les grossistes étrangers — le modèle d'escrow y est peu pertinent pour des transactions individuelles. Sabon Gari regroupe des vendeurs plus familiers du numérique et des paiements électroniques, et les articles (chaussures importées, mode premium) ont une valeur unitaire plus élevée, ce qui justifie davantage l'usage d'un service d'escrow.
**Alternatives considérées :**
- Kantin Kwari — écarté (contrefaçons dominantes, vendeurs moins tech-savvy, tickets moyens potentiellement inférieurs)
- Les deux en parallèle — écarté (dispersion des ressources du pilote, profils vendeurs trop différents)
**Décidé par :** CEO Orchestrator sur la base de la recherche marché (source : `docs/08_research/market/reviewed/2026-05-05_kano-whatsapp-commerce-review.md`).
**Impact :** GO_TO_MARKET.md, FIELD_TEST_PLAN.md, MVP_SCOPE.md, USER_JOURNEYS.md.
**Réversibilité :** Facilement réversible — expansion à Kantin Kwari possible en Phase 2 si le pilote Sabon Gari est concluant.

---

### 2026-05-05 [OPÉRATIONS] — Adoption du modèle concierge pour les 4 premières semaines du pilote
**Décision :** Pendant les 4 premières semaines du pilote Phase 1, l'équipe AmanaTrade (ou son relais local) accompagnera physiquement les vendeurs lors de leurs premières transactions sécurisées.
**Contexte :** La recherche recommande ce modèle pour résoudre les bugs en temps réel, rassurer les early adopters, et collecter des données comportementales impossibles à obtenir à distance. C'est une méthode d'amorçage classique pour les marketplaces.
**Alternatives considérées :**
- Onboarding entièrement autonome dès le départ — écarté (risque de taux d'abandon élevé sur les premières frictions)
- Tutoriels vidéo en haoussa uniquement — écarté (insuffisant pour rassurer des vendeurs peu familiers avec la fintech)
**Décidé par :** CEO Orchestrator sur la base de la recherche marché.
**Impact :** FIELD_TEST_PLAN.md, GO_TO_MARKET.md, HUMAN_ACTIONS.md (nécessite un relais local à Kano).
**Réversibilité :** Le modèle concierge est par nature temporaire — il sera abandonné dès que le taux d'activation dépasse 60 % sans intervention humaine.

---

### 2026-05-05 [FINANCE] — Hypothèse de commission : 2,5–3 % pour le segment détail
**Décision :** L'hypothèse de commission à tester lors du pilote est fixée à **2,5 % à 3 %** du montant de la transaction pour le segment détail, avec un minimum forfaitaire de **500 ₦**.
**Contexte :** Cette fourchette est alignée avec les benchmarks des services d'escrow nigérians existants (EscrowLock, Peppa.io : 1,25 %–3,25 %). Elle est retenue comme hypothèse haute pour le segment détail, justifiée par l'inclusion d'une garantie de résolution de litiges. Elle doit être validée terrain.
**Alternatives considérées :**
- Commission < 1,5 % — écarté pour le MVP (non rentable compte tenu des coûts PSP ~1,5 %)
- Commission > 3,5 % — écarté (risque de résistance des vendeurs, non validé par les benchmarks)
- Abonnement mensuel vendeur — écarté pour le MVP (non validé terrain, modèle non éprouvé dans ce segment)
**Décidé par :** CEO Orchestrator sur la base de la recherche marché. Validation terrain Phase 1 obligatoire avant de figer le taux.
**Impact :** BUSINESS_MODEL.md, FINANCIAL_MODEL.md.
**Réversibilité :** Facilement révisable après les interviews vendeurs Phase 1.
**Décision associée en attente :** D-P1 (modèle de revenus final) reste à trancher après validation terrain.

---

## Décisions en attente (à trancher)

| # | Décision | Domaine | Bloquée par | Urgence |
|---|----------|---------|-------------|---------|
| D-P1 | Modèle de revenus : commission par transaction vs abonnement vendeur vs hybride | Stratégie / Finance | Recherche + validation terrain | 🔴 Bloquant |
| D-P2 | Partenaire de paiement principal : **Monnify ou Squad (candidats identifiés)** vs autres | Tech / Finance | Validation légale CBN de l'architecture + test sandbox | 🔴 Bloquant |
| D-P3 | Structure légale : opérer via entreprise française, nigériane, ou partenaire local ? | Légal | Consultation avocat nigérian | 🔴 Bloquant |
| D-P4 | Mécanisme de séquestre : **architecture Hold & Release via PSP licencié (hypothèse)** vs **Trust Account bancaire (Option E)** | Légal / Tech | Avis avocat CBN (Question explicite sur Option B vs Option E) | 🔴 Bloquant |
| D-P5 | Recrutement : développeur freelance vs agence vs CTO co-fondateur | Opérations | Décision fondateur (budget, réseau) | 🟡 Phase 2 |
| D-P6 | Politique de litige : délais, critères de remboursement, clause de juridiction Kano | Opérations / Produit / Légal | Décision fondateur + Legal Agent + avocat local Kano | 🟡 Phase 1 |
| D-P7 | Compatibilité finance islamique / Wakalah : communication officielle ou non ? | Stratégie / Légal | Avis juriste islamique nigérian + validation terrain | 🟡 Phase 1 |
| D-P8 | Timing création filiale CAC Nigeria : avant pilote ou avant lancement commercial ? | Légal | Consultation avocat nigérian (question prioritaire) | 🔴 Bloquant |
| D-P9 | Flux KYC MVP : concevoir pour Tier 1 (≤ ₦20 000) uniquement, ou prévoir Tier 2 dès le MVP ? | Produit / Légal | Validation terrain ticket moyen réel + avis avocat sur vérification physique adresse | 🟡 Phase 1 |
| D-P10 | Intégration co-fondateur/investisseur nigérian pour Startup Act (≥ 33,3 % capital) | Finance / Légal | Décision fondateur après analyse dilution | 🟢 Phase 2 |

---

## Décisions à ne pas prendre maintenant

Ces sujets ont été identifiés mais doivent être délibérément mis de côté jusqu'à la fin de la Phase 0 :

- Architecture technique détaillée (stack, framework) → attendre clarification légale et choix PSP
- Stratégie de levée de fonds externe → attendre validation terrain Phase 1
- Expansion à Kaduna, Sokoto, Maiduguri → attendre Phase 3
- Catégories produit additionnelles → attendre fin Phase 2

---

*Alimenté par tous les agents après chaque décision structurante. Piloté par le CEO Orchestrator.*
