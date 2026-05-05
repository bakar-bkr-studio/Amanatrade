# USER JOURNEYS — AmanaTrade

## Objectif de ce document
Documenter les parcours utilisateurs clés, étape par étape, du point de vue de l'utilisateur.

> **Note :** Ces parcours sont des hypothèses basées sur la recherche documentaire. Ils doivent être validés et enrichis par les interviews terrain (Phase 1). Les noms "Aisha" (vendeuse, Sabon Gari) et "Ibrahim" (acheteur, étudiant Bayero University) sont utilisés comme personas représentatifs.

---

## Parcours 1 — Transaction réussie (Happy Path)

### Acteurs : Vendeur Aisha + Acheteur Ibrahim
*Contexte : Ibrahim voit les chaussures de sport d'Aisha sur son WhatsApp Status. Ils ne se connaissent pas. Ibrahim hésite à payer à l'avance.*

| Étape | Acteur | Action | Point de contact | Émotion | Moment de confiance |
|---|---|---|---|---|---|
| 1 | Ibrahim | Voit les chaussures sur le WhatsApp Status d'Aisha | WhatsApp Status | Intéressé mais méfiant — "Et si ce n'est pas ce qui est affiché ?" | — |
| 2 | Ibrahim | Envoie un message à Aisha pour se renseigner sur le prix et la pointure | WhatsApp message | Curieux, encore incertain | — |
| 3 | Aisha | Répond avec le prix (₦42 000) et crée une transaction AmanaTrade dans la PWA | PWA — espace vendeur | Confiante, habituée | — |
| 4 | Aisha | Partage le lien AmanaTrade dans la conversation WhatsApp : *"Kana iya biyan kuɗi a nan lafiya" (Tu peux payer ici en toute sécurité)* | WhatsApp | — | **1er moment de confiance : lien AmanaTrade légitime** |
| 5 | Ibrahim | Ouvre le lien : voit la description de la transaction, les garanties AmanaTrade, le prix | PWA — vue acheteur | Rassuré — "AmanaTrade bloque mon argent, je serai remboursé si le produit est faux" | **2e moment de confiance : garantie de remboursement visible** |
| 6 | Ibrahim | Saisit son numéro de téléphone, valide son BVN (Tier 1 — KYC léger) | PWA | Légère friction — mais acceptable | — |
| 7 | Ibrahim | Effectue le virement vers le NUBAN (DVA) affiché — depuis son application bancaire | Application bancaire | Anxieux le temps du virement | — |
| 8 | Système | Webhook reçu : paiement confirmé. Notification SMS + PWA envoyée à Aisha et Ibrahim | SMS / PWA | Ibrahim soulagé. Aisha prête à expédier. | **3e moment de confiance : confirmation immédiate** |
| 9 | Aisha | Emballe les chaussures, les remet à Peng Logistics. Déclare l'expédition dans la PWA. | PWA — espace vendeur / Peng | Engagée | — |
| 10 | Ibrahim | Reçoit la livraison (J+1 ou J+2). Inspecte les chaussures. | Physique | Soulagé — les chaussures sont conformes | — |
| 11 | Ibrahim | Confirme la réception dans la PWA en 1 clic | PWA — vue acheteur | Satisfait | **4e moment de confiance : contrôle de l'acheteur jusqu'au dernier instant** |
| 12 | Système | Fonds libérés automatiquement vers le compte d'Aisha (Disbursement API) | PSP → compte vendeur | — | **5e moment de confiance : Aisha reçoit ses fonds sans litige** |
| 13 | Aisha | Reçoit la notification de virement reçu | SMS / Application bancaire | Satisfaite | — |

**Points de friction principaux :**
- Étape 6 : KYC léger perçu comme une contrainte — doit être ultra-rapide (BVN = 10 secondes)
- Étape 7 : Anxiété du virement vers un compte inconnu — mitiger par le design (branding Amana rassurant)
- Étape 11 : Ibrahim doit confirmer dans un délai de 24h — risque d'oubli → SMS de rappel nécessaire

---

## Parcours 2 — Litige : acheteur non satisfait

### Acteurs : Vendeur Moussa + Acheteur Fatima
*Contexte : Fatima reçoit un tissu qui ne correspond pas à la description (couleur différente, qualité inférieure). Elle veut être remboursée.*

| Étape | Acteur | Action | Point de contact | Émotion |
|---|---|---|---|---|
| 1 | Fatima | Reçoit la livraison — le tissu est clairement différent des photos WhatsApp | Physique | Frustrée, indignée |
| 2 | Fatima | Ouvre la PWA AmanaTrade via le lien de transaction original | PWA | Déterminée à se faire rembourser |
| 3 | Fatima | Clique sur "Ouvrir un litige" — disponible pendant 24h après la livraison | PWA — vue acheteur | Inquiète — *"Est-ce que ça va vraiment marcher ?"* |
| 4 | Fatima | Soumet des preuves : photos du tissu reçu, capture des images WhatsApp de la description | PWA — formulaire litige | Frustrée mais coopérative |
| 5 | Système | Litige ouvert — les fonds restent bloqués. Notification à Moussa. | SMS + PWA | Fatima rassurée, Moussa surpris/inquiet |
| 6 | Moussa | Reçoit la notification de litige. Peut soumettre sa version (preuves d'expédition, photos) | PWA — espace vendeur | Stressé, sur la défensive |
| 7 | **Équipe AmanaTrade** | Analyse les preuves des deux parties (traitement manuel Phase 1). Délai max 48h. | Back-office | — |
| 8 | **Équipe AmanaTrade** | Décision : tissu non-conforme prouvé → remboursement total à Fatima | Système admin | — |
| 9 | Système | Remboursement déclenché vers le compte de Fatima. Notification Moussa et Fatima. | SMS + Application bancaire | Fatima soulagée. Moussa déçu mais informé. |
| 10 | Fatima | Reçoit son remboursement en 24-48h | Application bancaire | Confiance renforcée en AmanaTrade |

**Points de friction principaux :**
- Délai de 48h de résolution peut sembler long — communication proactive indispensable
- Moussa peut percevoir le système comme biaisé vers l'acheteur — les CGU doivent définir clairement les critères
- La collecte de preuves (photos) peut être difficile sur mobile bas de gamme — le formulaire doit être simple

---

## Parcours 3 — Vendeur : inscription et première transaction

### Acteur : Vendeur Binta (première fois sur AmanaTrade)
*Contexte : Binta vend des Abayas sur WhatsApp depuis Sabon Gari. Une collègue lui a recommandé AmanaTrade. Elle n'a jamais utilisé de service de paiement sécurisé.*

| Étape | Acteur | Action | Point de contact | Émotion |
|---|---|---|---|---|
| 1 | Binta | Clique sur le lien AmanaTrade reçu de sa collègue (ou trouvé via Startup Kano) | WhatsApp / Web | Curieuse mais méfiante |
| 2 | Binta | Consulte la page d'accueil PWA — en haoussa. Comprend la promesse : *"Tsaron kuɗin kasuwancin ku"* | PWA — landing page | Intriguée, plus confiante |
| 3 | Binta | S'inscrit : numéro de téléphone → OTP SMS → BVN (Tier 1) | PWA — inscription | Légère friction. BVN demandé = moment de résistance potentiel |
| 4 | Binta | **Modèle concierge :** un agent AmanaTrade l'appelle pour l'aider à compléter son profil (Phase 1) | Appel téléphonique | Rassurée par le contact humain |
| 5 | Binta | Crée sa première transaction : saisit la description de son Abaya, le prix (₦25 000), le délai de livraison | PWA — espace vendeur | Surprise par la simplicité |
| 6 | Binta | Copie le lien généré et l'envoie à son cliente Hauwa via WhatsApp | WhatsApp | Confiante |
| 7 | Hauwa | Paie via USSD (pas d'application bancaire). Confirmation reçue en 2 minutes. | USSD + SMS | — |
| 8 | Binta | Reçoit la notification de paiement sécurisé. Expédie l'Abaya avec Peng Logistics. | PWA + SMS | Soulagée — l'argent est garanti avant l'expédition |
| 9 | Binta | Reçoit ses fonds 26h après la livraison (24h délai acheteur + temps de virement) | Application bancaire | Satisfaite, convertie |

**Points de friction principaux :**
- Étape 3 : BVN obligatoire peut créer une hésitation — nécessite de l'expliquer clairement
- Étape 4 (Phase 1 seulement) : le modèle concierge ne sera pas scalable — à documenter comme coût opérationnel temporaire
- Le délai entre livraison et réception des fonds (~26h) peut être perçu comme long vs virement instantané habituel

---

## Parcours 4 — Acheteur : première utilisation

### Acteur : Ibrahim (acheteur, étudiant Bayero University)
*Contexte : Ibrahim n'a jamais utilisé AmanaTrade. Il reçoit un lien dans une conversation WhatsApp avec une vendeuse qu'il ne connaît pas. Il a déjà été arnaqué une fois il y a 3 mois.*

| Étape | Acteur | Action | Point de contact | Émotion |
|---|---|---|---|---|
| 1 | Ibrahim | Reçoit un message WhatsApp d'une vendeuse : *"Kana iya biyan kuɗi a nan" + lien AmanaTrade* | WhatsApp | Méfiant — "C'est quoi ce lien ?" |
| 2 | Ibrahim | Vérifie l'URL du lien avant de cliquer (domaine amanatrade.ng visible dans l'aperçu WhatsApp) | WhatsApp (aperçu lien) | Légèrement rassuré |
| 3 | Ibrahim | Ouvre le lien : page transaction en haoussa — description article, montant ₦18 500, délai 2j, garanties | PWA — vue acheteur | Surpris — l'interface est en haoussa, ça rassure |
| 4 | Ibrahim | Lit la section "Garanties AmanaTrade" : *"Idan kaya bai zo ba, za a mayar da kuɗin ka"* (Si la marchandise n'arrive pas, ton argent sera restitué) | PWA | Confiance en hausse — cela répond à son doute principal |
| 5 | Ibrahim | Saisit son numéro de téléphone → reçoit un OTP → procède au paiement | PWA | Léger stress — virement vers inconnu |
| 6 | Ibrahim | Choisit le paiement par virement bancaire (NUBAN affiché). Ouvre son application bancaire dans un autre onglet. | Application bancaire | Familier avec le virement — méthode normale |
| 7 | Ibrahim | Effectue le virement. Attend la confirmation. | Application bancaire | Anxieux les 3 premières minutes |
| 8 | Système | SMS reçu : *"Ibrahim, kuɗin ka an tsare shi a AmanaTrade. Za a saki shi bayan karɓar kayan."* (Ton argent est en sécurité chez AmanaTrade. Il sera libéré après réception des articles.) | SMS | Soulagé — première expérience positive |
| 9 | Ibrahim | Reçoit la livraison J+2 — les baskets sont conformes | Physique | Satisfait |
| 10 | Ibrahim | Clique sur "Confirmer la réception" dans la PWA (reçoit un rappel SMS 3h avant expiration du délai 24h) | PWA + SMS | Satisfait, confiant |
| 11 | Ibrahim | Partage son expérience à 3 amis sur WhatsApp | WhatsApp | Ambassadeur spontané |

**Points de friction principaux :**
- Étape 3 : Le premier contact avec l'interface — si le haoussa n'est pas parfait ou si le design n'est pas rassurant, Ibrahim repart
- Étape 5 : L'OTP et la saisie du numéro sont obligatoires — le parcours doit être < 60 secondes
- Étape 10 : Ibrahim peut oublier de confirmer — le SMS de rappel est indispensable pour éviter les litiges liés à l'expiration

---

## Points de friction identifiés (synthèse — à traiter en design)

| # | Friction | Parcours concerné | Action design |
|---|---|---|---|
| F-01 | BVN demandé lors de l'inscription — peur de partager des données bancaires | P3 (vendeur) | Expliquer clairement l'usage du BVN (vérification d'identité uniquement, pas de débit) |
| F-02 | Anxiété du virement vers un NUBAN inconnu | P1, P4 (acheteur) | Design rassurant avec logo Amana + explication de l'escrow avant le virement |
| F-03 | Doute sur la légitimité du lien AmanaTrade (peur de phishing) | P4 (acheteur) | URL officielle visible dans l'aperçu WhatsApp, certificat SSL, design cohérent |
| F-04 | Oubli de confirmation de réception (délai 24h) | P1, P4 (acheteur) | SMS de rappel 6h et 1h avant expiration du délai |
| F-05 | Délai de 24-48h pour recevoir les fonds (vendeur) | P1, P3 (vendeur) | Communication explicite sur le délai dès l'inscription. Comparer vs COD (zéro garanti). |
| F-06 | Résistance au KYC (Tier 2 pour transactions >₦20k) | P3, P1 (chaussures) | Parcours Tier 2 fluide — pièce d'identité photographiée en 30 secondes |
| F-07 | Difficulté à réunir les preuves lors d'un litige | P2 (acheteur) | Bouton "Signaler un problème" accessible pendant la transaction, guide photo simple |

---

## Moments de confiance clés (à renforcer en design)

| # | Moment | Parcours | Design recommandé |
|---|---|---|---|
| MC-01 | Premier aperçu du lien WhatsApp (URL + titre de la transaction) | P1, P4 | URL mémorable (amanatrade.ng), titre en haoussa, pastille verte |
| MC-02 | Page transaction : garanties lisibles en haoussa avant de payer | P1, P4 | Section "Garanties" en première position, texte court, icône bouclier |
| MC-03 | Confirmation de paiement en temps réel (SMS < 2 min) | P1, P4 | SMS en haoussa, mention du nom du vendeur, montant, délai |
| MC-04 | Déclaration d'expédition visible pour l'acheteur | P1 | Statut de suivi : Payé → Expédié → Livré → Fonds libérés |
| MC-05 | Bouton "Confirmer la réception" — acheteur maître du déclenchement final | P1, P4 | CTA clair, visible, en haoussa. Message après clic : "Kuna gode, farin cikin kasuwanci!" |
| MC-06 | Libération des fonds confirmée au vendeur | P1, P3 | SMS + notification PWA : montant exact reçu, dans X minutes |

---

*Responsable : Product & UX Agent*
*Mis à jour : 2026-05-05 — après analyse recherche marché Kano*
*Sources : docs/08_research/market/reviewed/2026-05-05_kano-whatsapp-commerce-review.md*
*Validation terrain requise : Interviews Phase 1 — voir HUMAN_ACTIONS.md*
