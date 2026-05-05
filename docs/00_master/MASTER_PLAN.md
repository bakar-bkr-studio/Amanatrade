# MASTER PLAN — AmanaTrade

## Objectif de ce document
Centraliser la feuille de route du projet à haut niveau : phases, jalons, priorités actuelles et dépendances critiques entre domaines.

---

## Phase actuelle
> **Phase 0 : Structuration stratégique & levée des incertitudes bloquantes**
> Statut : En cours — *Initialisé le 2026-05-05*

---

## Vision du projet

AmanaTrade est une infrastructure de confiance pour le commerce social au Nigeria du Nord.

Le produit initial est une PWA mobile-first qui sécurise les transactions WhatsApp entre vendeurs professionnels et acheteurs particuliers via un flux de séquestre (escrow-like).

**Nom** : AmanaTrade — du mot haoussa *amana* (confiance, dépôt de confiance).

---

## Phases du projet

### Phase 0 — Structuration stratégique (actuelle)
**Objectif** : Lever les incertitudes critiques avant de dépenser quoi que ce soit sur le produit.

- [x] Structure HQ initialisée (repo amanatrade-hq)
- [x] Vision, cible et contraintes MVP définies
- [x] Décisions fondatrices actées (voir DECISION_LOG.md)
- [ ] Modèle économique finalisé et validé
- [ ] Cadre légal CBN pour l'escrow clarifié (avocat nigérian)
- [ ] Architecture technique de haut niveau validée
- [ ] Comparatif APIs de paiement Nigeria produit
- [ ] Recherche marché WhatsApp commerce Kano lancée
- [ ] Questions pour avocat rédigées et envoyées

**Critère de sortie de Phase 0** : Les 3 questions bloquantes sont résolues — légal escrow, modèle économique, flux de paiement technique.

---

### Phase 1 — Validation du concept (terrain)
**Objectif** : Confirmer la demande réelle et l'adoption avant de coder.

- [ ] Interviews de 20 vendeurs WhatsApp à Kano (vêtements/chaussures)
- [ ] Interviews de 20 acheteurs WhatsApp à Kano
- [ ] Identification d'un partenaire local opérationnel à Kano
- [ ] Test de la proposition de valeur : l'acheteur paie-t-il pour la confiance ?
- [ ] Identification du canal d'acquisition primaire (agents terrain, bouche-à-oreille, WhatsApp groups)
- [ ] Documentation des objections et freins à l'adoption
- [ ] Décision : continuer vers MVP ou pivoter

**Critère de sortie de Phase 1** : Au moins 10 vendeurs déclarent être prêts à utiliser le service et 30 % des acheteurs interviewés expriment une intention de payer.

---

### Phase 2 — MVP & test terrain Kano
**Objectif** : Déployer la version minimale fonctionnelle et valider le comportement réel.

- [ ] PRD finalisé et validé
- [ ] MVP Scope verrouillé (voir MVP_SCOPE.md)
- [ ] Développeur(s) recruté(s) ou prestataire sélectionné
- [ ] Repo applicatif créé séparément
- [ ] PWA développée : création de transaction, paiement, confirmation, libération
- [ ] Intégration API paiement validée (Paystack ou Flutterwave)
- [ ] Interface Hausa finalisée
- [ ] Test avec 10 transactions réelles à Kano
- [ ] Collecte de feedback terrain structurée
- [ ] Analyse des incidents : litiges, abandons, bugs

**Budget indicatif Phase 2** : ≤ 5 000 € (dans le plafond des 10 000 €)

**Critère de sortie de Phase 2** : 50 transactions complètes sans incident grave. Taux de complétion > 70 %.

---

### Phase 3 — Itération & densification Kano
**Objectif** : Améliorer le produit et atteindre une masse critique à Kano.

- [ ] Corrections priorisées post-test terrain
- [ ] Acquisition de 100 vendeurs actifs à Kano
- [ ] Système de réputation/avis implémenté
- [ ] Données de rétention et NPS collectées
- [ ] Modèle économique validé par les revenus réels (commission, abonnement ?)
- [ ] Documentation des unités économiques : CAC, LTV, churn

**Critère de sortie de Phase 3** : Modèle économique prouvé, unités économiques positives, base utilisateur stable.

---

### Phase 4 — Expansion régionale Nigeria du Nord
**Objectif** : Répliquer le modèle dans d'autres villes du Nord (Kaduna, Sokoto, Maiduguri…).

- [ ] Playbook d'expansion défini (recrutement d'agents locaux, onboarding vendeurs)
- [ ] Capacité technique à scaler (infrastructure, support multilingue)
- [ ] Stratégie de financement externe validée (grants, impact investors, VC local)
- [ ] Équipe locale recrutée

---

## Priorités de la semaine en cours

> Semaine du 2026-05-05

1. 🔴 Lancer les recherches marché : taille WhatsApp commerce à Kano, ticket moyen, taux de litige
2. 🔴 Clarifier le cadre légal CBN pour l'escrow — rédiger les questions pour l'avocat
3. 🟡 Finaliser le comparatif APIs de paiement Nigeria (Paystack, Flutterwave, Monnify, Squad)
4. 🟡 Identifier un premier contact ou partenaire local à Kano
5. 🟢 Compléter les fichiers de base (BUSINESS_MODEL, FINANCIAL_MODEL) avec des hypothèses chiffrées

---

## Blocages actifs

| # | Blocage | Domaine | Dépendance | Impact |
|---|---------|---------|------------|--------|
| B1 | Légalité du service escrow au Nigeria non confirmée | Légal | Consultation avocat CBN | Bloque la conception du flux de paiement et le modèle économique |
| B2 | Aucun partenaire local identifié à Kano | Opérations | Action humaine (réseau, LinkedIn, diaspora) | Bloque les interviews terrain et le test MVP |
| B3 | Modèle économique (commission vs abonnement) non tranché | Stratégie | Recherche + décision fondateur | Bloque les projections financières et la conception produit |
| B4 | Architecture de séquestre technique non validée | Tech | Résolution de B1 + B3 | Bloque le PRD final et la recherche de développeurs |

---

## Dépendances critiques inter-domaines

```
[Légal : clarification escrow CBN]
        ↓
[Tech : conception flux paiement]
        ↓
[Produit : PRD & MVP Scope finaux]
        ↓
[Finance : modèle économique & projections]
        ↓
[Marketing : pricing & proposition de valeur terrain]
        ↓
[Opérations : lancement Phase 1 terrain]
```

---

## Contraintes non négociables

- Budget maximum : 10 000 € contribution personnelle du fondateur
- Géographie initiale : Kano uniquement
- Catégories produit : vêtements et chaussures uniquement
- Cible : vendeurs WhatsApp professionnels + acheteurs particuliers
- Format : PWA mobile-first
- Langue : Hausa-first, anglais second
- Ce repo = documents stratégiques uniquement, jamais de code applicatif

---

*Mis à jour par : CEO Orchestrator — 2026-05-05*
