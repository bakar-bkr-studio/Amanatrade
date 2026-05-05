# ESCROW LEGAL OPTIONS — AmanaTrade

## Objectif de ce document
Analyser les options légales pour structurer le mécanisme de séquestre (escrow) au Nigeria sans enfreindre la réglementation de la Central Bank of Nigeria (CBN).

---

## Définition de l'escrow dans le contexte AmanaTrade
AmanaTrade retient temporairement le paiement de l'acheteur jusqu'à confirmation de réception satisfaisante de la marchandise, puis le libère au vendeur (moins commission).

---

## Questions légales centrales
1. Cette activité nécessite-t-elle une licence CBN spécifique ?
2. Peut-on structurer cela comme service de paiement intermédiaire ?
3. Un partenariat avec une fintech déjà licenciée est-il possible ?
4. Quelle entité légale détient les fonds en séquestre ?

---

## Options à analyser

### Option A — Licence propre CBN (MMO ou PSSP)
- **Description :** Obtenir une licence officielle de *Mobile Money Operator* (MMO) ou de *Payment Solution Service Provider* (PSSP) pour détenir légalement les fonds des clients.
- **Coûts & Conditions :** La licence MMO exige un capital social minimum de 2 milliards NGN. La licence PSSP exige 100 millions NGN.
- **Faisabilité pour le MVP :** **Inatteignable.** Les barrières financières et temporelles sont prohibitives pour une startup en phase de test.

### Option B — Partenariat avec PSP licencié (Architecture Split + Disbursement)
- **Description :** Utiliser les APIs de fractionnement (Split Payments) et de décaissement différé (Disbursement / Single Transfer) d'un Payment Service Provider (PSP) licencié par la CBN, tel que Monnify, Squad ou Flutterwave.
- **Fonctionnement :** L'acheteur paie sur un Compte Virtuel Dédié (DVA). Les fonds sont retenus dans les portefeuilles du PSP. AmanaTrade n'agit que comme orchestrateur logique. Sur confirmation de l'acheteur, AmanaTrade déclenche l'API de Disbursement pour libérer les fonds du sous-compte vers le compte bancaire du vendeur.
- **Viabilité :** **Haute.** C'est l'approche recommandée pour contourner l'exigence de licence tout en évitant le "commingling" (mélange des fonds). À valider formellement par un avocat.

### Option C — Escrow-as-a-Service tiers (Pandascrow, Vahlid, Peppa)
- **Description :** Intégrer une API tierce spécialisée dans l'escrow, qui possède déjà l'infrastructure légale.
- **Coûts :** Les frais sont très élevés (5% pour Pandascrow, 1.5% à 2.5% pour Vahlid).
- **Faisabilité :** **Faible.** L'accumulation de ces frais d'escrow avec les frais de passerelle de paiement asphyxierait les marges des petits vendeurs de vêtements et chaussures.

### Option D — Structure contractuelle *Wakalah* (Agence Islamique)
- **Description :** Structurer contractuellement AmanaTrade comme un simple "Wakeel" (agent) qui exécute un mandat au nom de l'acheteur et du vendeur en échange d'honoraires fixes ou d'une commission transparente (Ujrah).
- **Viabilité :** Complémentaire à l'Option B. Offre une justification éthique et culturelle forte pour le marché de Kano (compatibilité avec la finance islamique).
- **Risques :** À elle seule, cette structure ne dispense pas de la conformité réglementaire CBN concernant la détention de fonds (d'où la nécessité de combiner avec l'Option B). Non validée par un juriste islamique nigérian.

### Option E — Compte fiduciaire bancaire (Trust Account / Compte de cantonnement)
- **Description :** Les fonds payés par l'acheteur sont versés directement sur un compte fiduciaire ouvert auprès d'une banque commerciale partenaire (pas sur le compte AmanaTrade). AmanaTrade détient uniquement un "pouvoir d'instruction" sur ce compte via API : il peut déclencher le paiement au vendeur une fois la livraison confirmée, mais ne détient jamais les fonds.
- **Fonctionnement :** La banque partenaire est légalement la dépositaire des fonds. AmanaTrade est l'entité instructrice. Ce modèle est documenté dans la pratique d'escrow e-commerce nigériane.
- **Viabilité :** ⚠️ **Potentiellement plus solide légalement que l'Option B** (les fonds sont dans un compte bancaire nommément séparé, pas dans une infrastructure PSP), mais plus complexe à négocier et à intégrer techniquement. Nécessite un partenariat bancaire formel.
- **Différence avec Option B :** Option B = fonds dans portefeuilles/sous-comptes du PSP. Option E = fonds dans un compte fiduciaire bancaire dédié. Les deux évitent la détention directe par AmanaTrade.
- **Risques :** Nécessite un accord de compte fiduciaire avec une banque nigériane (UBA, GTB, Access Bank, etc.). Délais de négociation longs. Plus de friction pour la trésorerie.
- **À évaluer en parallèle de l'Option B** lors de la consultation juridique.

### Option F — Licence Super Agent (50 millions NGN capital)
- **Description :** AmanaTrade obtient une licence de "Super Agent" CBN pour gérer un réseau de points physiques à Kano où les acheteurs déposent des fonds et les vendeurs retirent leur paiement, en s'appuyant sur une banque partenaire pour la tenue de compte réelle.
- **Viabilité :** **Faible pour le MVP.** Capital de 50 M NGN reste élevé (~30 000 €). Ce modèle nécessite une infrastructure physique (agents terrain), contradictoire avec le concept PWA digital. Intéressant pour Phase 3+ si AmanaTrade veut adresser les populations sans accès bancaire.
- **Utilité à court terme :** Permet de résoudre le problème de la vérification physique d'adresse KYC Tier 1 si AmanaTrade dispose d'agents locaux à Kano.

---

## Recommandation provisoire
> **Hypothèse de travail (Phase 0) :**
> - **Architecture principale :** Option B (Split + Disbursement via PSP licencié — Monnify/Squad) pour la rapidité d'intégration
> - **Alternative à évaluer :** Option E (Trust Account bancaire) si l'avocat confirme une meilleure solidité légale
> - **Couche contractuelle :** Option D (Wakalah) — à intégrer dans les CGU après validation par un juriste islamique nigérian
> - **Non retenu pour MVP :** Options A (capital inatteignable), C (coût trop élevé), F (infrastructure physique requise)
>
> **⚠️ Ces conclusions sont des hypothèses de travail. Aucune ne peut être actée sans validation par un avocat nigérian qualifié en droit CBN.**
>
> **Action bloquante :** Voir `QUESTIONS_FOR_LAWYER.md` et `HUMAN_ACTIONS.md`.

---

*Responsable : Legal & Compliance Agent*
*Sources : `docs/08_research/payments/reviewed/2026-05-05_nigeria-payment-providers-review.md` + `docs/08_research/legal/reviewed/2026-05-05_nigeria-escrow-regulation-review.md`*
*Mis à jour le : 2026-05-05*
