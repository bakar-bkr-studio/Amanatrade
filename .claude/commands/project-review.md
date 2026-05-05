# Project Review — AmanaTrade HQ

Effectue une revue complète de l'état actuel du projet AmanaTrade HQ.

## Lecture obligatoire (dans cet ordre)

1. Lis `CLAUDE.md` — identité du projet, règles opérationnelles, structure attendue.
2. Lis `docs/00_master/MASTER_PLAN.md` — plan global et priorités.
3. Lis `docs/00_master/DECISION_LOG.md` — décisions prises et en attente.
4. Lis `docs/00_master/AGENT_QUESTIONS.md` — questions sans réponse.
5. Lis `docs/00_master/HUMAN_ACTIONS.md` — actions humaines requises.
6. Lis `docs/00_master/RESEARCH_BACKLOG.md` — recherches à faire.

## Analyse approfondie

### A. État des documents stratégiques

Pour chaque dossier de `docs/` (`01_strategy`, `02_finance`, `03_legal`, `04_product`, `05_tech`, `06_marketing_operations`, `08_research`) :
- **Complétude** : quels fichiers existent ? Lesquels manquent par rapport aux objectifs du CLAUDE.md ?
- **Qualité** : chaque document distingue-t-il clairement faits, hypothèses, recommandations et questions ouvertes ?
- **Cohérence** : les informations sont-elles cohérentes entre domaines ?

### B. Décisions bloquées

Identifie toutes les décisions bloquantes ou en attente dans `DECISION_LOG.md` et `AGENT_QUESTIONS.md`. Pour chacune, précise :
- Quel domaine est concerné (stratégie, finance, légal, produit, tech, marketing)
- Pourquoi elle est bloquée
- Ce qui est nécessaire pour la débloquer

### C. Préparation au handoff applicatif

Évalue l'avancement des 6 livrables de handoff vers le futur repo PWA :
- `docs/04_product/PRD.md`
- `docs/04_product/MVP_SCOPE.md`
- `docs/04_product/DESIGN_BRIEF.md`
- `docs/05_tech/TECH_ARCHITECTURE.md`
- `docs/05_tech/PAYMENT_FLOW.md`
- `docs/05_tech/DEVELOPMENT_HANDOFF.md`

Pour chaque fichier : existe-t-il ? Est-il complet ? Que manque-t-il ?

### D. Respect des règles opérationnelles

Vérifie que les 12 règles du CLAUDE.md sont respectées dans l'ensemble des documents :
- Pas de faits inventés
- Distinction faits / hypothèses / recommandations / questions ouvertes
- Informations manquantes signalées
- Recherches nécessaires ajoutées au backlog
- Questions ajoutées à `AGENT_QUESTIONS.md`
- Actions humaines trackées dans `HUMAN_ACTIONS.md`
- Scope MVP respecté (Kano, WhatsApp, vêtements/chaussures, petites valeurs)
- Pas de conclusions légales définitives

## Synthèse finale

Produis un rapport structuré en français avec :

**Statut général du projet**
Résumé en 3–5 phrases de là où en est AmanaTrade aujourd'hui.

**✅ Points forts**
Ce qui est bien avancé ou bien documenté.

**⚠️ Lacunes et zones de risque**
Informations manquantes, hypothèses non validées, zones floues.

**🔴 Blocages critiques**
Décisions ou recherches sans lesquelles le projet ne peut pas avancer.

**📋 Les 5 actions prioritaires suivantes**
Classées par urgence. Pour chacune : domaine concerné, action concrète, responsable (humain ou agent).

**📊 Score de maturité par domaine**
| Domaine | Score | Commentaire |
|---|---|---|
| Stratégie | 🔴 / 🟡 / 🟢 | … |
| Finance | 🔴 / 🟡 / 🟢 | … |
| Légal | 🔴 / 🟡 / 🟢 | … |
| Produit | 🔴 / 🟡 / 🟢 | … |
| Tech | 🔴 / 🟡 / 🟢 | … |
| Marketing & Ops | 🔴 / 🟡 / 🟢 | … |
| Recherche | 🔴 / 🟡 / 🟢 | … |

Légende : 🔴 Non démarré · 🟡 En cours · 🟢 Solide

## Règles d'exécution

- Ne pas créer de nouveaux fichiers sauf si explicitement demandé.
- Ne pas modifier les fichiers existants pendant la revue.
- Si le rapport doit être sauvegardé, écrire dans `docs/00_master/PROJECT_REVIEW.md` uniquement si l'utilisateur le confirme.
- Rédiger la synthèse en français.
- Ne pas inventer de données. Si une information est manquante, le signaler explicitement.
