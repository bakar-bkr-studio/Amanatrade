# MASTER PLAN — AmanaTrade HQ

*Ce document est la boussole centrale du projet. Il est mis à jour par le CEO Orchestrator à chaque session stratégique.*

---

## 1. Vision du projet

### Mission
Rendre le commerce social de confiance accessible à tous au Nigeria du Nord, en commençant par les vendeurs WhatsApp de Kano.

### Vision à 5 ans
AmanaTrade est l'infrastructure de confiance du commerce entre particuliers en Afrique de l'Ouest subsaharienne : des millions de transactions sécurisées chaque mois, une réputation bâtie dans chaque ville, dans chaque langue locale.

### Problème résolu
Dans le commerce WhatsApp informel à Kano, ni le vendeur ni l'acheteur ne se connaissent. Le vendeur craint de livrer sans paiement. L'acheteur craint de payer sans garantie de recevoir le produit. Il n'existe aucun mécanisme de confiance, aucun recours, aucun tiers.

**Le résultat** : des transactions abandonnées, des arnaques, un marché sous-exploité faute de confiance.

**La solution** : AmanaTrade joue le rôle de tiers de confiance numérique. L'acheteur paie dans un séquestre. Le vendeur livre. L'acheteur confirme. Les fonds sont libérés.

### Nom
*Amana* (أمانة) = confiance, dépôt de confiance, en arabe et en haoussa. Le nom porte la valeur fondamentale du produit.

---

## 2. Objectif du HQ stratégique

Ce dépôt (`amanatrade-hq`) est le **quartier général de la réflexion**. Il ne contient aucun code applicatif.

Son rôle :
- Centraliser la stratégie, les décisions et leur traçabilité
- Coordonner les travaux des agents IA spécialisés
- Produire les livrables nécessaires au développement de la PWA (PRD, architecture, brief design)
- Tracker les actions humaines et les recherches à réaliser
- Préparer le handoff vers le repo applicatif (Phase 2)

Agents disponibles dans ce HQ :
| Agent | Rôle |
|---|---|
| CEO Orchestrator | Pilotage, priorisation, cohérence globale |
| Research Manager | Recherches marché, légal, paiements, terrain |
| Business & Finance Agent | Modèle économique, budget, projections |
| Legal & Compliance Agent | Cadre juridique, CBN, KYC/AML, risques |
| Product & UX Agent | PRD, MVP scope, parcours utilisateurs, design brief |
| Tech Architecture Agent | Stack, architecture, flux de paiement, handoff |
| Marketing & Operations Agent | GTM, acquisition, terrain, litiges |

---

## 3. MVP cible

### Principe directeur
> Le MVP doit prouver UNE seule chose : un vendeur WhatsApp et un acheteur qui ne se connaissent pas peuvent conclure une transaction sécurisée via AmanaTrade, sans se faire confiance a priori.

### Ce que fait le MVP
1. L'acheteur initie une transaction via lien ou interface AmanaTrade
2. Il paie dans un séquestre sécurisé (pas directement au vendeur)
3. Le vendeur reçoit la notification et livre la marchandise
4. L'acheteur confirme la réception (ou déclenche un litige)
5. Les fonds sont libérés au vendeur (moins la commission AmanaTrade)

### Ce que le MVP ne fait PAS (hors scope)
| Feature | Raison de l'exclusion | Quand l'inclure |
|---|---|---|
| Système de réputation / avis vendeur | Complexité, données insuffisantes | Phase 3 |
| Livraison intégrée / logistique | Hors compétence cœur | Phase 3 |
| Marketplace (catalogue produits) | Hors scope social commerce | Phase 4 |
| Paiement par carte bancaire | Peu utilisé dans la cible | Phase 3 |
| Application iOS | Trop coûteux pour MVP | Phase 3 |
| Multi-catégories | Risque feature creep, complexité litiges | Phase 3 |
| Dashboard analytics vendeur | Pas critique pour la validation | Phase 2+ |

---

## 4. Utilisateurs ciblés

### Vendeurs (côté offre) — utilisateurs primaires
- Profil : petits commerçants professionnels opérant sur WhatsApp, Kano
- Activité principale : vente de vêtements et chaussures (neufs ou occasion)
- Revenu : TPE informelle, pas de système de caisse ni ERP
- Comportement : groupes WhatsApp, catalogues photo, négociation en chat
- Douleur principale : acheteurs qui refusent de payer à l'avance, arnaques, litiges non résolus
- Motivation à adopter AmanaTrade : protection du paiement + crédibilité vis-à-vis de l'acheteur

### Acheteurs (côté demande) — utilisateurs secondaires
- Profil : particuliers qui achètent via WhatsApp, Kano et périphérie
- Comportement : découverte via groupes WhatsApp, recommandations sociales
- Douleur principale : peur d'être escroqué, pas de recours après paiement
- Motivation à adopter AmanaTrade : garantie de remboursement si non-livraison

### Profil type — vendeur pilote idéal
- Actif sur WhatsApp depuis > 6 mois
- Réalise ≥ 5 transactions/mois
- Déjà eu au moins 1 litige ou transaction abandonnée
- Parle haoussa, semi-alphabétisé en anglais
- Téléphone Android, connexion 3G/4G

---

## 5. Zone géographique

### Phase MVP : Kano uniquement
**Justification :**
- 2ème plus grande ville du Nigeria (~4M habitants)
- Capitale commerciale du Nord Nigeria
- Fort usage WhatsApp dans le commerce informel
- Population majoritairement haoussa — cohérence linguistique
- Réseau de marchés structurés (Kantin Kwari pour vêtements, Sabon Gari pour chaussures)

### Hors scope Phase 0-2
- Abuja, Lagos, Kaduna : expansion Phase 4 uniquement
- Marchés ruraux : infrastructure insuffisante, hors budget

---

## 6. Produits et catégories MVP

### Inclus dans le MVP
- **Vêtements** : boubous, robes, tenues traditionnelles, vêtements importés
- **Chaussures** : sandales, chaussures formelles, sneakers

### Exclus du MVP
- Électronique (risque fraude élevé)
- Alimentation (périssable, logistique incompatible)
- Bijoux (valeur difficile à estimer, litiges complexes)
- Immobilier, véhicules (hors portée)

**Raison des limites** : les vêtements et chaussures ont des tickets moyens modestes, sont facilement inspectables à la livraison, et représentent le cœur des transactions WhatsApp à Kano.

---

## 7. Stratégie de recherche

### Priorité absolue (Phase 0)
Les 3 recherches suivantes bloquent toute progression vers la Phase 1 :

1. **Cadre légal CBN — escrow et paiements électroniques** *(Bloquant)*
   - Pilotée par : Legal & Compliance Agent + Research Manager
   - Output : `docs/08_research/legal/reviewed/cbn-escrow-regulation.md`

2. **Marché WhatsApp commerce Kano — taille, comportements, prix** *(Bloquant)*
   - Pilotée par : Research Manager
   - Output : `docs/08_research/market/reviewed/kano-whatsapp-commerce.md`

3. **Comparatif APIs de paiement Nigeria** *(Bloquant)*
   - Pilotée par : Research Manager + Tech Architecture Agent
   - Output : `docs/08_research/payments/reviewed/payment-apis-comparison.md`

### Recherches importantes (Phase 0-1)
4. Analyse concurrentielle — solutions de confiance commerce social Afrique de l'Ouest
5. Benchmarks modèles de revenus — escrow et paiement en marchés émergents
6. Partenaires locaux potentiels à Kano (associations, incubateurs, ONG)
7. Structure légale pour opérer au Nigeria depuis l'étranger

### Recherches de fond (Phase 1)
8. Contraintes techniques terrain (smartphones, connectivité Kano)
9. Comportements de paiement mobile au Nord Nigeria
10. Finance islamique et compatibilité sharia du modèle AmanaTrade

*Voir le détail dans `RESEARCH_BACKLOG.md`.*

---

## 8. Stratégie juridique

### Situation actuelle
Aucune validation légale. Le cadre réglementaire CBN pour les services d'escrow est inconnu.

### Approche
1. **Ne rien présumer** : pas de conclusion légale avant avis d'avocat qualifié
2. **Prioriser la clarification** : la légalité du mécanisme de séquestre est le blocage n°1
3. **Explorer les options** (voir `ESCROW_LEGAL_OPTIONS.md`) :
   - Option A : licence propre CBN (PSB ou Payment Solution Service)
   - Option B : partenariat avec PSP déjà licencié (Paystack, Flutterwave)
   - Option C : modèle d'agent de paiement
   - Option D : structure contractuelle sans licence (évaluation des risques)

### Hypothèse de travail (à valider)
L'option B (partenariat PSP licencié) est la plus probable pour un MVP avec budget limité. Le PSP porte la licence et la détention des fonds ; AmanaTrade orchestre le flux sans détenir les fonds directement.

### Actions légales prioritaires
1. Trouver et briefer un avocat nigérian spécialisé fintech/CBN
2. Transmettre `docs/03_legal/QUESTIONS_FOR_LAWYER.md`
3. Décider de la structure légale (entité nigériane CAC ou autre)
4. Clarifier les obligations KYC/AML pour les vendeurs

---

## 9. Stratégie finance & financement

### Contrainte fondatrice
Budget personnel maximum : **10 000 €**. Aucune dette, aucun investisseur externe pour les Phases 0 et 1.

### Allocation cible du budget (hypothèse)
| Poste | Montant estimé | Phase |
|---|---|---|
| Recherches et conseil juridique | 500–1 500 € | Phase 0 |
| Interviews terrain (déplacements, logistique) | 500–1 000 € | Phase 1 |
| Développement PWA (freelance) | 3 000–5 000 € | Phase 2 |
| APIs, hébergement, outils (12 mois) | 500–1 000 € | Phase 2 |
| Réserve incidents / imprévus | 1 000–2 000 € | — |
| **Total** | **≤ 10 000 €** | |

*Ces chiffres sont des hypothèses. À affiner avec `STARTUP_BUDGET.md`.*

### Modèle de revenus pressenti
**Commission par transaction** : AmanaTrade prélève X % sur chaque transaction sécurisée.
- Hypothèse de départ : 2–5 % du montant (à valider par les interviews)
- Décision finale : après benchmarks et test de sensibilité terrain

### Chemin vers le financement externe
- Phase 0-1 : autofinancement
- Phase 2 : si validation terrain positive → rechercher grants tech for good, impact investors Nigeria
- Phase 3+ : levée de fonds seed si les métriques le justifient

*Voir `FINANCIAL_MODEL.md` et `FUNDING_OPTIONS_ANALYSIS.md` pour le détail.*

---

## 10. Stratégie produit & UX

### Principes
- **Simple d'abord** : chaque écran doit être compréhensible par un vendeur semi-alphabétisé en anglais
- **Haoussa-first** : toute l'interface principale en haoussa, anglais en support
- **Mobile-only** : optimisé pour écrans 5–6 pouces, Android 8+, réseau 3G instable
- **Confiance visible** : chaque étape du flux doit rassurer (confirmation, statuts clairs, numéros de transaction)
- **Litige simple** : la politique de résolution des litiges doit être explicable en une phrase

### Flux MVP (happy path)
```
Acheteur → initie transaction → paie dans séquestre
         → Vendeur notifié → livre la marchandise
         → Acheteur confirme réception → fonds libérés au vendeur
```

### Flux alternatif (litige)
```
Acheteur ne confirme pas → déclenche litige dans X jours
         → AmanaTrade arbitre → décision dans Y heures
         → Remboursement ou libération des fonds
```

### Documents produit à remplir
- `docs/04_product/PRD.md` — Product Requirements Document complet
- `docs/04_product/MVP_SCOPE.md` — périmètre précis du MVP
- `docs/04_product/USER_JOURNEYS.md` — parcours acheteur et vendeur
- `docs/04_product/DESIGN_BRIEF.md` — contraintes et orientations design

*Ces fichiers sont la priorité du Product & UX Agent en Phase 0-1.*

---

## 11. Stratégie technique

### Décision actée
Format : **PWA mobile-first** (Progressive Web App)
- Accessible via lien WhatsApp sans installation
- Compatible Android 8+, Chrome/WebView
- Évite les frictions de l'App Store

### Stack technique (décisions ouvertes)
Aucune décision de stack n'est prise à ce stade. Le Tech Architecture Agent proposera les options après :
1. Clarification du choix PSP (impacte l'intégration backend)
2. Clarification légale (impacte la gestion des fonds)
3. Budget développeur confirmé

### Contraintes techniques non négociables
- Connexion réseau : fonctionnel en 3G lente, dégradé acceptable en 2G
- Performance : chargement < 3 secondes sur réseau 3G
- Sécurité : aucune donnée de paiement stockée côté client
- Accessibilité offline : statut de transaction visible sans connexion

### Handoff prévu
Le HQ produira pour le repo applicatif :
- `TECH_ARCHITECTURE.md` finalisé
- `PAYMENT_FLOW.md` finalisé
- `DEVELOPMENT_HANDOFF.md` — document d'entrée pour le développeur

---

## 12. Stratégie marketing & opérations

### Approche d'acquisition — Phase 1 (terrain)
**Hypothèse principale** : L'adoption se fera par confiance sociale, pas par marketing digital.

Canaux prioritaires à tester :
1. **Associations de commerçants de Kano** — accès groupé à des dizaines de vendeurs
2. **Bouche-à-oreille WhatsApp** — un vendeur convaincu recrute ses contacts
3. **Présence physique dans les marchés** — Kantin Kwari, Sabon Gari
4. **Agents terrain** — recrutement d'un ou deux relais locaux payés à la commission

### Message clé (hypothèse à tester terrain)
**Pour le vendeur** (en haoussa) : *"Karɓi kuɗinka tukuna, ka ba kaya bayan haka."*
("Ton argent est sécurisé d'abord, tu livres ensuite.")

**Pour l'acheteur** (en haoussa) : *"Ka biya cikin aminci. In ba a kai maka ba, za a mayar da kuɗinka."*
("Paie en sécurité. Si tu ne reçois pas, on te rembourse.")

### Gestion des litiges
Politique simple et explicable à l'avance :
- Délai de confirmation : 48h après livraison déclarée
- Délai de résolution : 72h après ouverture d'un litige
- Critère de remboursement : non-livraison prouvée ou produit non-conforme
- *Voir `DISPUTE_RESOLUTION_POLICY.md` pour le détail.*

---

## 13. Ordre de travail recommandé

### Séquence Phase 0 (maintenant)

```
Semaine 1-2
├── [LÉGAL] Rédiger et envoyer les questions à l'avocat (QUESTIONS_FOR_LAWYER.md)
├── [RECHERCHE] Lancer la recherche marché WhatsApp Kano
└── [RECHERCHE] Lancer le comparatif APIs de paiement Nigeria

Semaine 3-4
├── [LÉGAL] Réception avis avocat → mise à jour ESCROW_LEGAL_OPTIONS.md
├── [RECHERCHE] Synthèse marché → mise à jour kano-whatsapp-commerce.md
└── [FINANCE] Remplir hypothèses FINANCIAL_MODEL.md avec données recherche

Semaine 5-6
├── [PRODUIT] Remplir PRD.md et MVP_SCOPE.md complets
├── [PRODUIT] Remplir USER_JOURNEYS.md
├── [TECH] Finaliser TECH_ARCHITECTURE.md et PAYMENT_FLOW.md
└── [DÉCISION] Trancher modèle de revenus et choix PSP
```

### Critère de passage Phase 0 → Phase 1
Toutes les cases suivantes cochées :
- [ ] Avis avocat reçu sur la légalité de l'escrow
- [ ] Modèle de revenus décidé
- [ ] PSP pressenti identifié
- [ ] PRD v1 complet
- [ ] Partenaire local Kano identifié
- [ ] Budget de Phase 1 confirmé (< 2 000 €)

---

## 14. Risques principaux

| # | Risque | Probabilité | Impact | Mitigation |
|---|--------|-------------|--------|------------|
| R1 | L'escrow est illégal sans licence CBN coûteuse | Moyen | Critique | Explorer Option B (PSP partenaire). Avis avocat urgent. |
| R2 | Les vendeurs refusent de payer une commission | Moyen | Critique | Tester la sensibilité au prix en interview terrain. Commencer avec une commission symbolique. |
| R3 | Pas de partenaire local à Kano → interviews impossibles | Moyen | Élevé | Activer réseau diaspora haoussa, LinkedIn, incubateurs Nigeria. |
| R4 | Budget de développement insuffisant | Faible | Élevé | Cadrer le scope MVP au strict minimum. Co-fondateur technique ou bourse tech. |
| R5 | Fuite de données utilisateurs / failles sécurité | Faible | Critique | Chiffrement, hébergement conforme, pas de stockage local des données de paiement. |
| R6 | Contraintes de finance islamique (sharia) bloquent l'adoption | Inconnu | Élevé | Inclure dans les interviews terrain. Explorer modèle conforme si nécessaire. |
| R7 | PSP partenaire modifie ses conditions ou ferme | Faible | Élevé | Contractualiser, prévoir PSP alternatif. Ne pas dépendre d'un seul fournisseur. |

---

## 15. Prochaines actions immédiates

> Semaine du 2026-05-05

| Priorité | Action | Responsable | Livrable attendu |
|---|---|---|---|
| 🔴 1 | Trouver un avocat nigérian spécialisé CBN/fintech | Fondateur | Contact établi, briefing envoyé |
| 🔴 2 | Lancer la recherche marché WhatsApp Kano | Research Manager | `kano-whatsapp-commerce.md` (draft) |
| 🔴 3 | Lancer le comparatif APIs de paiement Nigeria | Research Manager | `payment-apis-comparison.md` (draft) |
| 🟡 4 | Identifier un premier partenaire ou contact local à Kano | Fondateur | Nom + coordonnées d'un relais local |
| 🟡 5 | Remplir les hypothèses de FINANCIAL_MODEL.md | Business & Finance Agent | Tableau unit economics rempli |
| 🟡 6 | Remplir PRD.md v1 avec flux MVP complet | Product & UX Agent | PRD fonctionnel v1 |
| 🟢 7 | Ouvrir un compte bancaire dédié au projet | Fondateur | Compte ouvert, suivi des 10 000 € |

---

## Contraintes non négociables (rappel permanent)

| Contrainte | Valeur |
|---|---|
| Budget personnel max | 10 000 € |
| Géographie Phase 0-2 | Kano uniquement |
| Catégories MVP | Vêtements et chaussures uniquement |
| Utilisateurs | Vendeurs WhatsApp + acheteurs particuliers |
| Format | PWA mobile-first |
| Langue | Haoussa-first, anglais second |
| Ce repo | Documents stratégiques — jamais de code applicatif |

---

*Mis à jour par : CEO Orchestrator — 2026-05-05*
*Prochaine mise à jour recommandée : après réception de l'avis avocat et des résultats de recherche marché*
