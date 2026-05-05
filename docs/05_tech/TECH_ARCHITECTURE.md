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

## Stack technique (décisions partiellement informées — à finaliser après validation légale)

| Composant | Option(s) envisagée(s) | Statut | Raison |
|---|---|---|---|
| Frontend | React / Vue / Svelte | À décider | Dépend du profil du développeur recruté |
| Backend | Node.js / Python (FastAPI) | À décider | Node.js préféré pour les évènements Webhook asynchrones |
| Base de données | PostgreSQL / Supabase | À décider | Besoin d'un audit log transactionnel fiable |
| Hébergement | Render / Railway / VPS | À décider | Préférer une région Africa ou Europe proche |
| **API Paiement** | **Monnify ou Squad (priorité 1)** | **Candidats identifiés** | **DVA permanents + Split API + Settlement rapide — voir PAYMENT_FLOW.md** |
| Auth / KYC | Monnify KYC API (BVN ~10 NGN, NIN ~60 NGN) | Candidat identifié | Exigence CBN Tier 1 non négociable |
| Notifications | Push PWA + SMS (Termii / Africa's Talking) | À décider | Push pour utilisateurs avec PWA installée, SMS pour fallback |
| Offline | Service Workers + IndexedDB | À implémenter | Architecture Offline-First obligatoire pour Kano |
| Partage WhatsApp | Web Share API (navigator.share()) | Retenu | Permet l'intégration native WhatsApp sans dépendance Meta API |

---

## Flux de données principal
*Voir PAYMENT_FLOW.md pour le détail*

---

## Exigences de sécurité
- Chiffrement des données de paiement en transit et au repos
- Audit log de toutes les transactions
- *À compléter*

---

## Contraintes techniques terrain — Kano (données confirmées par la recherche)

| Contrainte | Donnée | Source | Implication technique |
|---|---|---|---|
| Réseau dominant | MTN (latence 96ms), Airtel (141ms), Glo (plus lent) | Opensignal 2025 | Concevoir pour MTN, tester sur Airtel/Glo |
| Qualité connexion | 3G variable, zones périphériques Kano peu couvertes | IJEMH + terrain | PWA Offline-First obligatoire (Service Workers) |
| Appareils | Android 8+, 2–3 Go RAM, écrans 5–6 pouces | Estimation terrain | Performance budget strict : charge < 3s sur 3G |
| Cartes SIM | Utilisateurs souvent multi-SIM (MTN + Airtel) | Contexte local | Ne pas lier l’identité à un seul numéro de téléphone |
| Portefeuilles mobiles | OPay et PalmPay très adoptés | Multiple sources | Compatibilité OPay/PalmPay à tester avec le DVA du PSP |
| USSD | +252M transactions H1 2024, fonctionnel sans internet | CBN stats | Flux de paiement doit être compatible USSD |
| WhatsApp | Canal principal de négociation commerciale | Contexte terrain | Intégration via Web Share API, pas Meta Business API (MVP) |

---

## Décisions techniques à prendre
*À remplir — avec référence à DECISION_LOG.md et AGENT_QUESTIONS.md*

---

*Responsable : Tech Architecture Agent*
*Dépendances : PAYMENT_FLOW.md, MVP_SCOPE.md, LEGAL_RISK_REGISTER.md*
