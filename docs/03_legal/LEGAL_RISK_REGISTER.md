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

### R001 [PAIEMENTS] — Licence CBN pour service d'escrow
**Description :** Opérer un service de séquestre de fonds sans licence CBN pourrait être illégal.
**Probabilité :** Élevée
**Impact :** Élevé — Blocage complet de l'activité
**Réglementation concernée :** CBN Payment Service Providers Regulations
**Statut de l'analyse :** À vérifier
**Mitigation possible :** Partenariat avec une entité déjà licenciée CBN.
**Action requise :** QUESTIONS_FOR_LAWYER.md

### R002 [KYC/AML] — Exigences d'identification des utilisateurs
**Description :** Insuffisance du KYC expose à des risques de conformité AML/CFT.
**Probabilité :** Moyenne
**Impact :** Élevé
**Réglementation concernée :** CBN AML/CFT Regulations, EFCC Act
**Statut de l'analyse :** À vérifier
**Mitigation possible :** Intégration NIN/BVN Nigeria dès le MVP.
**Action requise :** QUESTIONS_FOR_LAWYER.md

### R003 [DONNÉES] — Conformité NDPR
**Description :** Collecte et stockage de données personnelles soumis à la NDPR.
**Probabilité :** Élevée
**Impact :** Moyen
**Réglementation concernée :** Nigeria Data Protection Regulation (NDPR) 2019
**Statut de l'analyse :** À vérifier
**Mitigation possible :** Politique de confidentialité conforme, stockage données au Nigeria.
**Action requise :** QUESTIONS_FOR_LAWYER.md

---

## Risques à analyser
*À compléter par le Legal & Compliance Agent*

---

*Responsable : Legal & Compliance Agent*
*Dépendances : docs/08_research/legal/*
