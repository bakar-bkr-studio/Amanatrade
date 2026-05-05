# CLAUDE.md — AmanaTrade HQ

## Identité du projet
**AmanaTrade** est une startup fintech/social commerce dont la mission est de sécuriser les transactions entre petits vendeurs professionnels et acheteurs particuliers au nord du Nigeria (pilote : Kano). Le MVP cible les vendeurs WhatsApp de vêtements et chaussures. Le produit sera une PWA mobile-first, en haoussa et anglais.

---

## Ce dossier est un QG stratégique — pas un repo applicatif
- Ne pas créer de code applicatif ici.
- Ne pas créer de repo app ici.
- Tout le travail ici est documentaire, stratégique et de recherche.

---

## Règles générales

### Langue
- Les documents stratégiques et internes sont rédigés en **français**.
- Les documents destinés à des partenaires/investisseurs internationaux peuvent être en **anglais**.
- Les documents de recherche terrain ou de marketing peuvent inclure du **haoussa**.

### Qualité des informations
- Toute information factuelle doit être sourcée. Voir `docs/08_research/SOURCE_QUALITY_RULES.md`.
- Distinguer clairement : fait vérifié / hypothèse / à vérifier.
- Ne jamais présenter une hypothèse comme un fait.

### Fichiers centraux à alimenter systématiquement
Chaque agent, chaque session de travail doit mettre à jour ces fichiers :

| Fichier | Quand l'alimenter |
|---|---|
| `docs/00_master/DECISION_LOG.md` | Toute décision structurante prise |
| `docs/00_master/AGENT_QUESTIONS.md` | Toute question ouverte identifiée |
| `docs/00_master/HUMAN_ACTIONS.md` | Toute action nécessitant une intervention humaine |
| `docs/00_master/RESEARCH_BACKLOG.md` | Tout sujet nécessitant une recherche approfondie |

### Demande de validation
- Avant de créer un fichier non listé dans la structure officielle, demander validation au fondateur.
- Avant de prendre une décision stratégique majeure, la soumettre pour validation via `DECISION_LOG.md`.

### Intégrité des agents
- Les agents ne se substituent pas au fondateur pour les décisions finales.
- Les agents signalent les risques, les angles morts, et les incertitudes.
- Les agents ne font pas de promesses sur des données non vérifiées.

---

## Structure des dossiers

```
amanatrade-hq/
  CLAUDE.md              ← Ce fichier. Règles générales.
  README.md              ← Présentation du projet.
  .claude/agents/        ← Rôles et instructions des agents IA.
  docs/00_master/        ← Pilotage central du projet.
  docs/01_strategy/      ← Vision, modèle économique, business plan.
  docs/02_finance/       ← Budget, financement, modèle financier.
  docs/03_legal/         ← Risques juridiques, options légales, questions avocat.
  docs/04_product/       ← PRD, scope MVP, parcours utilisateurs, design.
  docs/05_tech/          ← Architecture technique, flux de paiement, handoff dev.
  docs/06_marketing_operations/ ← GTM, test terrain, politique de litiges.
  docs/08_research/      ← Protocole recherche, index, données brutes et validées.
```

---

## Contexte marché (point de départ)
- Marché cible initial : Kano, nord Nigeria
- Segment : vendeurs WhatsApp (vêtements, chaussures)
- Problème central : absence de mécanisme de confiance / séquestre entre inconnus
- Modèle pressenti : commission sur transaction sécurisée
- Contraintes réglementaires : CBN (Central Bank of Nigeria), lois sur l'escrow, KYC/AML

---

*Dernière mise à jour : 2026-05-05*
