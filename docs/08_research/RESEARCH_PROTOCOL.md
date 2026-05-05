# RESEARCH PROTOCOL — AmanaTrade

## Objectif de ce document
Définir comment les recherches sont menées, documentées, et validées dans ce projet.

---

## Principe général
Toute décision stratégique doit s'appuyer sur des données vérifiables. Les hypothèses sont acceptables, mais doivent être explicitement labellisées comme telles.

---

## Étapes du processus de recherche

### 1. Identification du besoin
- Sujet ajouté dans `docs/00_master/RESEARCH_BACKLOG.md`
- Priorité assignée (🔴 / 🟡 / 🟢)

### 2. Recherche brute (raw)
- Fichier créé dans le sous-dossier approprié : `docs/08_research/[domaine]/raw/`
- Nom du fichier : `AAAA-MM-JJ_sujet-court.md`
- Contenu : toutes les sources trouvées, brutes, avec URL et date d'accès
- Pas de synthèse à ce stade : juste de la collecte

### 3. Revue et validation (reviewed)
- Fichier synthèse créé dans : `docs/08_research/[domaine]/reviewed/`
- Application des règles de SOURCE_QUALITY_RULES.md
- Chaque donnée labellisée : ✅ Vérifié / ⚠️ À confirmer / ❌ Incertain
- Contradictions signalées explicitement

### 4. Mise à jour de l'index
- Entrée ajoutée dans `docs/08_research/RESEARCH_INDEX.md`
- Backlog mis à jour (statut → Terminé)

---

## Sous-dossiers disponibles
- `finance/` — marchés financiers, unit economics, données bancaires Nigeria
- `legal/` — réglementation CBN, droit des paiements, NDPR, escrow
- `market/` — taille du marché, comportements utilisateurs, concurrents
- `payments/` — APIs de paiement, infrastructures bancaires Nigeria

---

*Responsable : Research Manager*
