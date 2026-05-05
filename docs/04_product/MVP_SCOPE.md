# MVP SCOPE — AmanaTrade

## Objectif de ce document
Définir précisément ce qui est DANS et HORS du MVP. Ce document protège contre le feature creep.

---

## Principe directeur
> Le MVP doit prouver UNE chose : un vendeur WhatsApp et un acheteur inconnu l'un de l'autre peuvent conclure une transaction sécurisée via AmanaTrade, sans se faire confiance a priori.

---

## Périmètre du MVP

- **Géographie :** Kano uniquement (priorité : marché Sabon Gari)
- **Catégories :** chaussures et vêtements uniquement
- **Utilisateurs :** vendeurs WhatsApp professionnels + acheteurs particuliers
- **Volume cible Phase 1 :** 10 à 30 vendeurs actifs
- **Format :** PWA mobile-first (Progressive Web App), accès via lien WhatsApp

---

## Ce qui est DANS le MVP

### Flux principal (happy path)

| Étape | Acteur | Action | Canal |
|---|---|---|---|
| 1 | **Vendeur** | Crée une transaction AmanaTrade (description article, montant, délai de livraison) | PWA — espace vendeur |
| 2 | **Vendeur** | Partage le lien de transaction généré directement à l'acheteur | WhatsApp (message direct ou Status) |
| 3 | **Acheteur** | Ouvre le lien, consulte les détails de la transaction (article, montant, garanties) | PWA — vue acheteur |
| 4 | **Acheteur** | Effectue le paiement via virement bancaire (DVA NUBAN) ou USSD | PSP (Monnify/Squad) |
| 5 | **Système** | Confirme la réception du paiement (Webhook) — notifie le vendeur | PWA + SMS/WhatsApp |
| 6 | **Vendeur** | Confirme l'expédition dans la PWA (déclaration d'envoi) | PWA — espace vendeur |
| 7 | **Acheteur** | Reçoit la livraison et confirme dans la PWA (ou délai d'attente expire) | PWA — vue acheteur |
| 8 | **Système** | Libère les fonds au vendeur (Disbursement API) après confirmation ou délai | PSP → compte vendeur |

**Délai de confirmation acheteur :** 24h après livraison (délai à valider terrain). Si l'acheteur ne répond pas dans le délai, les fonds sont libérés automatiquement au vendeur.

### Fonctionnalités incluses

**Côté Vendeur**
- [ ] Inscription et vérification KYC basique (BVN + NIN — Tier 1 pour transactions ≤ ₦20 000)
- [ ] Inscription KYC Tier 2 (pièce d'identité officielle — pour transactions chaussures >₦20 000)
- [ ] Création d'une transaction (titre, description, montant, durée)
- [ ] Génération d'un lien de transaction partageable (deep link WhatsApp)
- [ ] Tableau de bord simple : transactions en cours, complétées, litiges
- [ ] Notification de paiement reçu (SMS + notification PWA)
- [ ] Déclaration d'expédition (déclenchement du délai acheteur)
- [ ] Réception des fonds après confirmation ou expiration délai

**Côté Acheteur**
- [ ] Accès via lien WhatsApp (sans inscription préalable pour consulter)
- [ ] Inscription légère lors du paiement (téléphone + KYC Tier 1 minimal)
- [ ] Vue transaction : détails article, montant, délai, vendeur
- [ ] Paiement via virement bancaire NUBAN (DVA)
- [ ] Paiement via USSD (pour utilisateurs sans application bancaire)
- [ ] Confirmation de réception du produit (déclenche libération fonds)
- [ ] Ouverture de litige si article non conforme

**Gestion de litige (version minimaliste)**
- [ ] Acheteur peut ouvrir un litige dans les 24h après livraison
- [ ] Litige traité **manuellement** par l'équipe AmanaTrade en Phase 1 (pas d'automatisation)
- [ ] Résolution : remboursement total OU libération au vendeur selon preuves (photos, échanges WhatsApp)
- [ ] Délai de résolution cible : 48h

**Administration (back-office minimal)**
- [ ] Dashboard admin : liste des transactions, statuts, litiges ouverts
- [ ] Outil de résolution manuelle des litiges
- [ ] Accès aux logs de paiement PSP

**Langue**
- [ ] Interface en haoussa (langue principale)
- [ ] Interface en anglais (langue secondaire)

---

## Ce qui est HORS du MVP (décisions conscientes)

| Feature exclue | Raison de l'exclusion | Quand l'inclure |
|---|---|---|
| **Système de notation / avis vendeur** | Complexité, risque de manipulation, hors scope preuve de concept | Phase 2 |
| **Paiement par carte bancaire** | Taux de conversion faible dans la cible, friction OTP/3DS | Phase 3 si la cible évolue |
| **Paiement OPay / PalmPay natif** | Compatibilité DVA non encore validée — à tester sandbox | Phase 2 si test concluant |
| **Automatisation des litiges (IA)** | Volume Phase 1 trop faible, expertise humaine suffisante | Phase 3 |
| **Catalogue vendeur / boutique en ligne** | Hors périmètre escrow, concurrence indirecte avec Instagram | Phase 3 |
| **App native Android / iOS** | Délai + coût inutile si la PWA convertit | Phase 3 si adoption > 1 000 vendeurs |
| **Multi-catégories** | Limite la complexité des litiges (garanties différentes par catégorie) | Phase 3 |
| **Abonnement vendeur** | Non validé terrain | Phase 2 si demande confirmée |
| **Expansion hors Kano** | Validation du modèle Kano d'abord | Phase 4 |
| **Fonctionnalité vocale (haoussa)** | Utile pour les moins alphabétisés mais complexe à développer | Phase 3 |
| **Intégration Instagram / TikTok** | Hors périmètre lien WhatsApp direct | Phase 3 |
| **Retours & reverse logistics** | Politique complexe, litiges difficiles — à définir avant d'automatiser | Phase 2 |

---

## Critères d'entrée (avant de commencer le développement)

- [ ] Validation légale du mécanisme d'escrow par un avocat nigérian CBN (architecture Hold & Release)
- [ ] Architecture PSP choisie et testée en sandbox (Monnify ou Squad — DVA + Webhook + Disbursement)
- [ ] Budget de développement confirmé (3 000–5 000 €)
- [ ] Développeur ou agence PWA identifié et briefé
- [ ] KYC Tier 1 et Tier 2 : procédure d'onboarding validée (BVN/NIN intégration)
- [ ] Politique de litige minimale rédigée et validée par le fondateur
- [ ] Au moins 5 vendeurs pilotes confirmés à Kano (Sabon Gari)
- [ ] Partenaire logistique local confirmé (Peng Logistics ou Sendvoy)

---

## Critères de sortie du MVP (ce qui détermine le succès du test terrain)

| Métrique | Cible minimale | Cible aspirationnelle |
|---|---|---|
| Transactions sécurisées complétées | 30 transactions | 100 transactions |
| Vendeurs actifs sur 30 jours | 5 vendeurs | 15 vendeurs |
| Taux de litiges ouverts | < 20 % des transactions | < 10 % |
| Taux de résolution litiges ≤ 48h | 100 % | 100 % |
| Score de satisfaction vendeurs (1–5) | ≥ 3,5/5 | ≥ 4/5 |
| Score de satisfaction acheteurs (1–5) | ≥ 3,5/5 | ≥ 4/5 |
| Ticket moyen constaté | À mesurer | À mesurer |
| Taux de conversion acheteur (lien ouvert → paiement) | > 30 % | > 50 % |

---

## Contraintes techniques non négociables

- PWA < 200 KB initiale (compatibilité Android entrée de gamme, connexion 3G)
- Temps de chargement < 3 secondes sur réseau MTN 3G (latence ~96ms à Kano)
- Fonctionnement partiel hors-ligne (Service Workers + IndexedDB pour l'état des transactions)
- HTTPS obligatoire (confiance utilisateur)
- Pas de stockage de données de carte bancaire (hors scope)
- SMS fallback si notification PWA non reçue

---

*Responsable : Product & UX Agent*
*Validation requise : Fondateur avant gel du scope*
*Mis à jour : 2026-05-05 — après analyse recherche marché Kano*
*Sources : docs/08_research/market/reviewed/2026-05-05_kano-whatsapp-commerce-review.md*
