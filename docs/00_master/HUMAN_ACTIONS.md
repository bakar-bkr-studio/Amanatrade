# HUMAN ACTIONS — AmanaTrade

## Objectif de ce document
Lister toutes les actions qui ne peuvent être réalisées que par un humain (le fondateur ou une personne déléguée). Les agents IA ne peuvent pas faire ces actions à ta place.

---

## Format d'entrée

```
### [DATE] [DOMAINE] [PRIORITÉ : 🔴 Urgent / 🟡 Dès que possible / 🟢 Quand possible]
**Action :** Ce qui doit être fait concrètement.
**Pourquoi :** Contexte et impact sur le projet.
**Qui :** Fondateur / Partenaire local / Avocat / Autre.
**Avant quand :** Date limite ou dépendance.
**Statut :** À faire / En cours / Fait
```

---

## Actions à réaliser

### 2026-05-05 [LÉGAL] 🔴 — Trouver et briefer un avocat nigérian spécialisé en fintech et réglementation CBN
**Action :** Identifier un avocat (ou cabinet) nigérian avec une expertise en réglementation CBN, licences fintech, et droit des paiements. Lui transmettre le document `docs/03_legal/QUESTIONS_FOR_LAWYER.md` et obtenir des réponses écrites.
**Pourquoi :** La légalité du mécanisme d'escrow est le blocage n°1 du projet. Sans avis juridique, le flux de paiement, la structure légale, et le modèle économique ne peuvent pas être finalisés.
**Qui :** Fondateur (identification et premier contact). Possibilité de passer par le réseau diaspora haoussa, LinkedIn Nigeria, ou des plateformes comme Lawpadi.
**Avant quand :** Avant la fin de la Phase 0. Bloque la Phase 1.
**Statut :** À faire

---

### 2026-05-05 [MARCHÉ] 🔴 — Identifier et contacter un premier partenaire ou relais local à Kano
**Action :** Trouver une personne de confiance à Kano (membre de la diaspora haoussa, contact professionnel, partenaire d'une ONG locale, association de commerçants) capable de faciliter l'accès aux vendeurs WhatsApp pour les interviews terrain.
**Pourquoi :** Toute validation terrain nécessite une présence ou un relais local. AmanaTrade ne peut pas faire les interviews à Kano sans point d'ancrage. Ce contact est aussi utile pour valider les hypothèses culturelles et linguistiques.
**Qui :** Fondateur.
**Avant quand :** Avant le lancement de la Phase 1 (validation terrain).
**Statut :** À faire

---

### 2026-05-05 [FINANCE] 🟡 — Ouvrir un compte bancaire dédié au projet
**Action :** Ouvrir un compte bancaire séparé du compte personnel pour les dépenses AmanaTrade. Idéalement un compte professionnel ou un compte dédié avec suivi des entrées/sorties.
**Pourquoi :** Garder une traçabilité stricte des dépenses dans le plafond des 10 000 €. Indispensable pour le suivi du budget et pour une future levée de fonds.
**Qui :** Fondateur.
**Avant quand :** Avant toute première dépense projet.
**Statut :** À faire

---

### 2026-05-05 [OPÉRATIONS] 🟡 — Préparer et conduire 20 interviews vendeurs WhatsApp à Kano
**Action :** Concevoir un guide d'entretien (avec l'aide des agents), puis conduire ou faire conduire 20 interviews structurées avec des vendeurs WhatsApp actifs dans le segment vêtements/chaussures à Kano.
**Pourquoi :** C'est la validation terrain centrale de la Phase 1. Sans ces interviews, aucun chiffre de marché ni comportement utilisateur ne peut être affirmé.
**Qui :** Fondateur (en personne ou via partenaire local de confiance).
**Avant quand :** Phase 1 (après résolution du blocage légal et identification du partenaire local).
**Statut :** À faire

---

### 2026-05-05 [OPÉRATIONS] 🟡 — Préparer et conduire 20 interviews acheteurs WhatsApp à Kano
**Action :** Conduire ou faire conduire 20 interviews avec des acheteurs ayant déjà effectué un achat via WhatsApp à Kano (vêtements, chaussures ou autre).
**Pourquoi :** Comprendre le comportement d'achat côté demande : qui paie, combien, pourquoi hésite-t-on, quelle serait la volonté de payer pour un service de confiance.
**Qui :** Fondateur (en personne ou via partenaire local).
**Avant quand :** Phase 1 (en parallèle des interviews vendeurs).
**Statut :** À faire

---

### 2026-05-05 [TECH] 🟡 — Recruter un développeur ou identifier un prestataire technique pour la Phase 2
**Action :** Rechercher et évaluer des profils développeurs (freelance, agence, ou co-fondateur technique) capables de développer la PWA AmanaTrade. Comparer les coûts et disponibilités dans le budget disponible.
**Pourquoi :** Le développement ne peut pas commencer sans ressource technique. Ce recrutement conditionne toute la Phase 2.
**Qui :** Fondateur.
**Avant quand :** Fin de Phase 1 (pour démarrer la Phase 2 sans délai).
**Statut :** À faire

---

### 2026-05-05 [LÉGAL] 🟢 — Évaluer la nécessité d'enregistrer une structure légale au Nigeria (CAC)
**Action :** Sur la base de l'avis de l'avocat, décider si AmanaTrade doit enregistrer une entité légale au Nigeria (Companies and Allied Matters Act - CAC) avant ou pendant la Phase 2.
**Pourquoi :** Un enregistrement CAC peut être nécessaire pour ouvrir un compte bancaire nigérian, signer des contrats avec des PSP, ou accéder à certains programmes de financement.
**Qui :** Fondateur (décision) + Avocat nigérian (exécution).
**Avant quand :** Avant le lancement du MVP (Phase 2).
**Statut :** À faire

---

### 2026-05-05 [STRATÉGIE] 🟢 — Décider du modèle de revenus : commission, abonnement, ou hybride
**Action :** Après réception des résultats des interviews terrain et des benchmarks de modèles économiques, trancher la décision sur le modèle de revenus d'AmanaTrade.
**Pourquoi :** Cette décision impacte la conception produit (affichage des frais), les projections financières, et la stratégie d'acquisition des vendeurs.
**Qui :** Fondateur.
**Avant quand :** Avant la finalisation du PRD (Phase 2).
**Statut :** À faire

---

### 2026-05-05 [PRODUIT] 🟡 — Préparer le guide d'entretien pour les interviews terrain vendeurs et acheteurs
**Action :** Rédiger (avec le Product & UX Agent) un guide d'entretien structuré pour les 20 interviews vendeurs et 20 interviews acheteurs de la Phase 1. Le guide doit couvrir : comportements de transaction actuels, expériences de litiges, sensibilité au prix, réaction à la proposition AmanaTrade, préférences de langue, contraintes techniques.
**Pourquoi :** Un guide d'entretien solide garantit des données comparables et actionnables. Sans cela, les interviews produisent des anecdotes non synthétisables.
**Qui :** Fondateur (validation finale) + Product & UX Agent (rédaction).
**Avant quand :** Avant le début des interviews Phase 1.
**Statut :** À faire

---

### 2026-05-05 [TECH] 🟢 — Cartographier le marché des développeurs freelance pour la Phase 2
**Action :** Explorer les plateformes (Toptal, Upwork, communautés dev Nigeria, réseau personnel) pour identifier des profils de développeurs web/PWA disponibles dans le budget estimé (3 000–5 000 €). Évaluer également la possibilité d'un co-fondateur technique.
**Pourquoi :** Le développement ne peut pas commencer en Phase 2 sans ressource technique identifiée. Mieux vaut cartographier le marché tôt pour éviter les délais.
**Qui :** Fondateur.
**Avant quand :** Fin de Phase 1.
**Statut :** À faire

---

## Actions complétées

### 2026-05-05 [GLOBAL] — Initialisation du QG stratégique AmanaTrade HQ
**Action :** Créer le repo `amanatrade-hq` avec la structure de dossiers et les fichiers initiaux.
**Complété le :** 2026-05-05
**Par :** Fondateur.

---

*Alimenté par tous les agents dès qu'une action humaine est identifiée. Piloté par le CEO Orchestrator.*
