# TECH ARCHITECTURE — AmanaTrade

## Objectif de ce document
Définir l'architecture technique du MVP AmanaTrade, les choix technologiques, et leurs justifications.

---

## Principe directeur
> Architecture minimale viable. Pas de sur-ingénierie pour le MVP. Priorité : fiabilité du flux de paiement et sécurité des fonds.

---

## Type de produit
- **PWA (Progressive Web App)** — Mobile-first, pas d'app store requis
- Cible : Android, navigateurs Chrome/WebView
- Accessibilité offline : à évaluer (voir RESEARCH_BACKLOG.md)

---

## Stack technique (décisions ouvertes)

| Composant | Option(s) envisagée(s) | Décision | Raison |
|---|---|---|---|
| Frontend | React / Vue / Svelte | *À décider* | |
| Backend | Node.js / Python / autre | *À décider* | |
| Base de données | *À évaluer* | *À décider* | |
| Hébergement | *À évaluer* | *À décider* | |
| API Paiement | Paystack / Flutterwave | *À décider* | |
| Auth / KYC | *À évaluer* | *À décider* | |

---

## Flux de données principal
*Voir PAYMENT_FLOW.md pour le détail*

---

## Exigences de sécurité
- Chiffrement des données de paiement en transit et au repos
- Audit log de toutes les transactions
- *À compléter*

---

## Contraintes techniques terrain
- Réseau : 2G/3G, connexions instables
- Appareils : Android 8+, 2-3 Go RAM, 16-32 Go stockage
- Batterie : optimisation pour usage prolongé sans recharge

---

## Décisions techniques à prendre
*À remplir — avec référence à DECISION_LOG.md et AGENT_QUESTIONS.md*

---

*Responsable : Tech Architecture Agent*
*Dépendances : PAYMENT_FLOW.md, MVP_SCOPE.md, LEGAL_RISK_REGISTER.md*
