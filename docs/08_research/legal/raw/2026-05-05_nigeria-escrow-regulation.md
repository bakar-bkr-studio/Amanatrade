# **Cadre réglementaire et stratégique du commerce social et des services de paiement fiduciaire au Nigeria : Analyse approfondie pour le projet AmanaTrade**

Le paysage financier du Nigeria traverse une phase de transformation structurelle profonde, impulsée par une volonté de modernisation technologique et d'inclusion financière sans précédent. Dans le cadre du développement d'AmanaTrade, une plateforme de commerce social ciblant les transactions via WhatsApp à Kano, il est impératif de comprendre que l'environnement réglementaire ne se limite pas à une simple conformité technique, mais s'inscrit dans une vision stratégique globale portée par la Banque Centrale du Nigeria (CBN). Cette vision, articulée notamment dans le document *Payments System Vision 2025* (PSV 2025), vise à faire du système de paiement nigérian un catalyseur de la croissance économique en favorisant l'innovation tout en garantissant la résilience et la sécurité des transactions.1 Le projet AmanaTrade, en se positionnant à l'intersection de la technologie mobile, du commerce informel et des mécanismes de sécurisation des paiements, doit naviguer entre des exigences fédérales strictes, des obligations de protection des données personnelles et les spécificités socio-juridiques du Nord du Nigeria, où les principes de la finance islamique et les structures de marché traditionnelles comme celles de Kano jouent un rôle prédominant.

## **La légalité de la détention temporaire de fonds et le cadre de la garde fiduciaire**

La question de savoir si une startup peut légalement détenir les fonds d'un acheteur de manière temporaire au Nigeria est au cœur de la structure opérationnelle d'AmanaTrade. Au regard de la réglementation actuelle, la réponse dépend de la détention d'une licence spécifique ou de l'existence d'un accord de partenariat formel avec une institution agréée. La Banque Centrale du Nigeria maintient une distinction rigoureuse entre les entités autorisées à accepter des dépôts ou à émettre de la monnaie électronique et celles qui se contentent de faciliter les services de paiement.

### **Le principe de non-commingling et la restriction sur la détention de fonds**

L'un des piliers de la surveillance de la CBN est la règle de "non-commingling" (non-mélange des fonds). Cette règle stipule qu'une entreprise ne peut pas mélanger les fonds des clients avec ses propres fonds opérationnels. Plus encore, la plupart des catégories de licences de prestataires de services de paiement (PSP), à l'exception notable des opérateurs de monnaie mobile (MMO), n'ont pas l'autorisation légale de détenir des fonds de clients, même temporairement.3 Pour une startup, détenir les fonds d'un acheteur dans l'attente d'une livraison sans posséder une licence de banque ou de MMO est considéré comme une activité bancaire sans licence, ce qui expose les fondateurs à des sanctions pénales et au gel immédiat des comptes bancaires par les autorités.3

La notion d'escrow (dépôt fiduciaire) est reconnue juridiquement au Nigeria comme un arrangement où un tiers indépendant détient des actifs en fiducie pour le compte des parties à une transaction jusqu'à ce que certaines obligations soient remplies.5 Dans la pratique actuelle du commerce électronique nigérian, les services d'escrow sont généralement fournis par des banques commerciales ou des fintechs titulaires d'une licence MMO. Les entreprises de services technologiques qui ne disposent pas de ces licences doivent impérativement s'associer à une banque pour que les fonds soient sécurisés dans un compte de dépôt au nom de l'institution financière, et non sur le compte de la startup elle-même.5

### **Évolution vers une réglementation spécifique de l'escrow**

Il n'existe pas encore de loi unique et exclusive régissant spécifiquement les prestataires de services d'escrow au Nigeria. Le secteur évolue actuellement sous l'égide des directives générales de la CBN en matière de protection des consommateurs et de lutte contre le blanchiment d'argent.5 Cependant, la CBN a exprimé, à travers le projet PSV 2025, son intention de surveiller les nouveaux produits et participants pour renforcer la sécurité et la fiabilité du système de paiement.2 En l'absence de cadre dédié, les pratiques de marché imposent l'exécution d'un accord d'escrow détaillant les droits, les obligations et les conditions de déblocage des fonds, souvent sous la supervision d'une banque partenaire qui agit comme agent de paiement final.5

## **Architecture des licences de la CBN et typologie des acteurs fintech**

Pour opérer légalement dans l'écosystème financier nigérian, AmanaTrade doit s'orienter vers l'une des catégories de licences définies par la circulaire de la CBN du 9 décembre 2020, révisée en 2021\. Ces catégories sont conçues pour éviter la concentration des risques et assurer une spécialisation des acteurs.

### **Les catégories de licences et les exigences de capital**

Le tableau suivant synthétise les principales licences susceptibles d'être pertinentes pour une activité de commerce social intégrant un flux de paiement sécurisé.

| Catégorie de Licence | Activités Autorisées | Capital Social Minimum (₦) | Dépôt de Garantie (Escrow) à la CBN |
| :---- | :---- | :---- | :---- |
| **Mobile Money Operator (MMO)** | Émission de monnaie électronique, création de portefeuilles, gestion de comptes de regroupement. | 2 Milliards 4 | 2 Milliards (remboursable) 6 |
| **Switching and Processing** | Routage des transactions entre banques et PSP, compensation et règlement. | 2 Milliards 3 | 2 Milliards (remboursable) 6 |
| **Payment Solution Service Provider (PSSP)** | Passerelles de paiement, agrégation de services marchands, services de paiement web. | 100 Millions 3 | 100 Millions (remboursable) 6 |
| **Payment Terminal Service Provider (PTSP)** | Déploiement et maintenance de terminaux de paiement (POS), formation des marchands. | 100 Millions 3 | 100 Millions (remboursable) 6 |
| **Super Agent** | Services bancaires par agent (Agent Banking), gestion de réseaux d'agents. | 50 Millions 3 | 50 Millions (remboursable) 6 |
| **Payment Service Bank (PSB)** | Dépôts, envois de fonds, transactions de faible valeur, focus sur l'inclusion financière. | 5 Milliards 7 | N/A |

### **Distinctions terminologiques et fonctionnelles**

La compréhension des nuances entre les termes utilisés par le régulateur est cruciale pour définir la stratégie de licence :

* **Escrow vs Wallet** : Un service d'escrow est un mécanisme de blocage temporaire de fonds lié à une transaction spécifique. Un "wallet" (portefeuille numérique) est un instrument de stockage de valeur qui permet de conserver des fonds sur le long terme, d'effectuer des transferts et des paiements multiples. Seuls les MMO et les banques peuvent légalement offrir des services de "wallet" au grand public au Nigeria.3  
* **PSSP vs Marketplace Payment** : Un PSSP fournit l'infrastructure technique pour traiter les paiements (passerelle). Un paiement de type "marketplace" implique souvent une fonction d'encaissement pour compte de tiers, ce qui nécessite une autorisation explicite de la CBN pour éviter d'être requalifié en activité de banque ou de MMO.  
* **Payment Facilitator vs Aggregator** : Un agrégateur (comme NIBSS ou UPSL) route les transactions entre différents processeurs.9 Un facilitateur de paiement (souvent un PSSP) simplifie l'inscription des marchands en utilisant son propre identifiant de marchand (MID) pour traiter les transactions de sous-marchands, bien que les Payfacs plus avancés attribuent des MID uniques pour un meilleur suivi.10  
* **Switching vs Mobile Money** : Le "switching" concerne l'infrastructure lourde de routage et de compensation entre institutions financières ; ces acteurs ne détiennent jamais de fonds de clients.11 Le "Mobile Money" concerne l'interaction directe avec l'utilisateur final pour des services financiers via mobile.

## **Modèles opérationnels : Partenariats et alternatives à la licence propre**

Compte tenu des exigences de capital extrêmement élevées pour obtenir une licence MMO (2 milliards de nairas), la plupart des startups en phase de démarrage adoptent des modèles alternatifs pour offrir un flux de paiement sécurisé.

### **Opérer via un prestataire (PSP) licencié**

Il est tout à fait possible, et même courant, d'opérer via un partenaire licencié sans posséder de licence propre de la CBN. Dans ce scénario, AmanaTrade agirait comme une interface technologique (PWA) intégrée aux API d'une banque ou d'un MMO.12 Cependant, cette approche n'exonère pas la startup de toute responsabilité réglementaire. La CBN exige que les fintechs obtiennent une autorisation préalable ou une lettre de "non-objection" avant de lancer des services en partenariat avec des institutions financières.12 De plus, le partenaire licencié est tenu, en vertu de la réglementation sur la protection des consommateurs, de s'assurer que ses partenaires non réglementés respectent les normes de transparence et d'éthique.5

### **Modèles d'escrow-like sans détention directe**

Pour éviter les contraintes liées à la détention de fonds, AmanaTrade peut structurer ses flux selon les modèles suivants :

1. **Le compte de cantonnement (Trust Account)** : Les fonds payés par l'acheteur sont versés directement sur un compte fiduciaire ouvert auprès d'une banque commerciale partenaire. AmanaTrade n'a qu'un pouvoir d'instruction sur ce compte (via API) pour déclencher le paiement au vendeur une fois la livraison confirmée.  
2. **La virtualisation des comptes** : Utilisation de comptes virtuels (Virtual Accounts) générés par un partenaire PSSP/Banque pour chaque transaction. L'argent reste dans l'infrastructure de la banque jusqu'à ce que les conditions contractuelles soient validées sur la plateforme AmanaTrade.  
3. **Le modèle de l'agent de paiement** : AmanaTrade peut obtenir une licence de "Super Agent" (50 millions de nairas de capital) pour gérer un réseau de points physiques à Kano où les acheteurs peuvent déposer des fonds et les vendeurs retirer leur paiement, tout en s'appuyant sur une banque pour la tenue de compte réelle.11

## **Exigences de conformité KYC et AML pour les transactions de détail**

Le Nigeria a considérablement renforcé ses protocoles de lutte contre le blanchiment d'argent (AML) et de connaissance du client (KYC) en 2024\. Pour AmanaTrade, qui traite avec de petits vendeurs et des particuliers, l'adoption d'une approche basée sur le risque est essentielle.

### **Le système KYC à trois niveaux (Three-Tiered KYC)**

La CBN autorise une flexibilité pour les transactions de faible valeur afin de ne pas freiner l'inclusion financière.13

| Niveau (Tier) | Type de Compte | Limite de Dépôt Unique | Limite de Solde Cumulé | Exigences d'Identification |
| :---- | :---- | :---- | :---- | :---- |
| **Niveau 1** | Valeur Faible | ₦20,000 | ₦200,000 | Nom, date de naissance, adresse, numéro de téléphone. Le numéro BVN ou NIN est désormais obligatoire et doit être validé.13 |
| **Niveau 2** | Valeur Moyenne | ₦50,000 | ₦500,000 | Exigences du Niveau 1 \+ pièce d'identité officielle vérifiée (passeport, permis de conduire, carte d'électeur).14 |
| **Niveau 3** | Valeur Élevée | Sans limite | Sans limite | Procédure de diligence raisonnable complète, vérification physique de l'adresse, preuve de l'origine des fonds pour les dépôts importants.13 |

Une mise à jour majeure de juin 2024 impose désormais aux fintechs de réaliser une vérification physique de l'adresse pour tous les niveaux de comptes, y compris le niveau 1, afin de renforcer la sécurité du système financier.13 Pour une startup opérant à Kano, cela peut impliquer des défis logistiques importants.

### **Surveillance des transactions et signalement**

Les fintechs doivent déployer des systèmes automatisés capables de détecter des schémas suspects, tels que le "structuring" (division d'une grosse somme en plusieurs petites transactions pour éviter les seuils de signalement) ou des mouvements de fonds anormalement rapides.16 Toute activité suspecte doit être signalée à l'Unité de Renseignement Financier du Nigeria (NFIU) dans un délai de 24 heures.16

## **Protection des consommateurs et gestion des litiges à Kano**

Le succès d'AmanaTrade repose sur la confiance entre des parties qui ne se connaissent pas. Le cadre juridique nigérian offre plusieurs leviers pour encadrer cette confiance.

### **Cadre fédéral et local**

Au niveau fédéral, la *Federal Competition and Consumer Protection Act* (FCCPA) de 2018 protège les consommateurs contre les pratiques commerciales déloyales, les publicités mensongères et les produits défectueux.18 À Kano, la *Kano State Consumer Protection Council* (KSCPC) joue un rôle actif. En 2025, le conseil a été restructuré pour mieux lutter contre l'exploitation du marché et la vente de produits de mauvaise qualité, notamment dans les marchés de textiles et de chaussures.19

### **Mécanismes de résolution des litiges**

Pour une plateforme de commerce social, la gestion des litiges (non-livraison, produit non conforme) doit être intégrée nativement dans la PWA.

* **Transparence des conditions** : Les termes du service doivent être disponibles en Haoussa et en Anglais, spécifiant clairement les délais de livraison et les modalités de remboursement.22  
* **Rôle du régulateur** : La CBN impose aux institutions financières de mettre en place des normes minimales pour une résolution rapide des litiges.1  
* **Arbitrage local** : À Kano, les tribunaux de la Charia ont compétence pour les litiges commerciaux entre musulmans (*Mu'amalat*).23 Cependant, les litiges impliquant des institutions financières agréées relèvent souvent de la compétence de la Haute Cour Fédérale, ce qui peut créer des conflits de juridiction si les contrats ne sont pas rédigés avec précision.24

## **Protection des données personnelles : Obligations sous la NDPA 2023**

La *Nigeria Data Protection Act* (NDPA) de 2023 est la législation de référence. Toute startup traitant les données de résidents nigérians doit s'y conformer, sous peine de sanctions lourdes (jusqu'à 2 % du chiffre d'affaires annuel ou 10 millions de nairas).17

### **Obligations du responsable de traitement**

1. **Base légale** : Le traitement des données doit reposer sur le consentement explicite, l'exécution d'un contrat ou une obligation légale (comme le KYC).26  
2. **Enregistrement auprès de la NDPC** : Les organisations traitant les données de plus de 200 personnes sur six mois doivent s'enregistrer auprès de la Commission de Protection des Données du Nigeria (NDPC).28 Les frais varient selon l'importance de l'organisation.  
3. **Désignation d'un DPO** : Les "Data Controllers of Major Importance" (dont font partie les fintechs) doivent nommer un délégué à la protection des données (DPO).3  
4. **Audit annuel** : Un audit de conformité doit être déposé chaque année auprès de la commission par l'intermédiaire d'une organisation de conformité certifiée (DPCO).31

### **Transferts transfrontaliers vers la France**

AmanaTrade étant pilotée par un fondateur basé en France, les données personnelles nigérianes peuvent être transférées ou consultées depuis l'Europe.

* **Décision d'adéquation** : La NDPA interdit le transfert de données vers un pays tiers sans un niveau de protection adéquat validé par la NDPC.32 Bien que l'UE (dont la France) dispose du RGPD, la liste d'adéquation nigériane est en cours de mise à jour sous le nouveau régime de 2025\.32  
* **Instruments contractuels** : En l'absence de décision d'adéquation formelle, AmanaTrade doit utiliser des clauses contractuelles types approuvées par la NDPC pour encadrer ces transferts.32

## **Risques juridiques et fiscaux pour un fondateur basé en France**

L'exploitation d'une startup nigériane depuis la France présente des défis spécifiques liés à la structure de l'entreprise et aux mouvements de capitaux.

### **Constitution et participation étrangère**

La loi nigériane (CAMA 2020\) interdit à une société étrangère de mener des affaires au Nigeria sans créer une filiale locale enregistrée auprès de la *Corporate Affairs Commission* (CAC).34

* **Capital social minimum** : Pour toute société avec une participation étrangère, le capital social minimum est fixé à **100 millions de nairas**.34 Ce montant ne doit pas nécessairement être déposé en une fois, mais il sert de base au calcul des droits d'enregistrement et des droits de timbre (0,75 % du capital).34  
* **Enregistrement NIPC** : La filiale doit obligatoirement être enregistrée auprès de la *Nigerian Investment Promotion Commission* pour garantir la protection de l'investissement et le droit au rapatriement des bénéfices.34

### **Rapatriement des bénéfices et fiscalité**

1. **Le certificat d'importation de capitaux (CCI)** : C'est le document le plus crucial pour un investisseur étranger. Lorsqu'un capital est injecté au Nigeria, la banque réceptrice doit émettre un CCI électronique dans les 24 à 48 heures.37 Sans ce certificat, il est illégal et pratiquement impossible de convertir des nairas en euros pour rapatrier des dividendes via le marché officiel.37  
2. **Convention fiscale Nigeria-France** : Il existe un accord pour éviter la double imposition.40 Cependant, le Nigeria applique une retenue à la source (Withholding Tax) sur les dividendes, les intérêts et les redevances. Depuis juillet 2022, le taux réduit préférentiel de 7,5 % a été abrogé, et le taux standard est désormais de **10 %**.41  
3. **Modernisation fiscale** : En 2026, un protocole d'accord a été signé entre le fisc nigérian (FIRS) et l'administration fiscale française (DGFiP) pour renforcer la capacité du Nigeria à suivre et taxer les revenus de l'économie numérique.44 Cela signifie que la transparence fiscale sera une exigence forte.

### **Opportunités liées au Nigeria Startup Act 2022**

Le *Nigeria Startup Act* offre des incitations majeures, mais impose une condition de propriété : pour obtenir le "Startup Label", une entreprise doit avoir au moins **un tiers (33,3 %)** de son capital détenu par des Nigérians.46 Les avantages incluent des exonérations fiscales de quatre ans, des crédits d'impôt pour les investisseurs et un accès facilité aux licences via un portail dédié.47

## **Recommandations pour un MVP prudent à Kano**

Pour lancer AmanaTrade de manière sécurisée et économique à Kano, la stratégie suivante est recommandée :

1. **Modèle de partenariat (API-first)** : Ne pas solliciter de licence MMO immédiatement. S'associer à une banque ou à un PSSP (comme Flutterwave, Paystack ou Moniepoint) pour utiliser leurs infrastructures de comptes virtuels et de garde de fonds.12  
2. **Focus sur le Niveau 1 KYC** : Limiter les transactions initiales aux seuils du Niveau 1 (dépôt max ₦20,000) pour simplifier l'onboarding des vendeurs de chaussures et de vêtements. Utiliser le numéro de téléphone lié au NIN/BVN pour la vérification.13  
3. **Conformité Charia "Mu'amalat"** : À Kano, la perception de la finance est religieuse. Il est recommandé de structurer le flux d'escrow comme un contrat d'agence (*Wakalah*) avec des frais de service fixes plutôt que des intérêts, et de consulter un expert local pour valider les termes du contrat.51  
4. **Hébergement et données** : Bien que la PWA soit pilotée depuis la France, privilégier un stockage des données critiques au Nigeria ou s'assurer que les clauses contractuelles de transfert sont en place dès le premier jour pour éviter les amendes de la NDPC.30  
5. **Présence locale minimale** : Nommer un directeur résident nigérian et un secrétaire général pour satisfaire aux exigences de la CAC et faciliter les interactions avec les autorités de Kano.12

## **Questions stratégiques pour un avocat spécialisé au Nigeria**

Lors de la consultation d'un cabinet juridique (ex: Templars, Aluko & Oyebode, ou G. Elias), les points suivants doivent être abordés :

1. "Quelles sont les clauses spécifiques à insérer dans nos conditions générales en Haoussa pour que le flux d'escrow soit reconnu comme un contrat de vente valide sous le droit de la Charia à Kano?"  
2. "Comment pouvons-nous structurer notre accord avec un partenaire MMO pour qu'AmanaTrade conserve le contrôle de l'expérience utilisateur tout en laissant la responsabilité de la garde des fonds au partenaire?"  
3. "Dans le cadre de la NDPA 2023, quel est le niveau de risque réel associé à la consultation des données KYC nigérianes par une équipe technique située en France?"  
4. "Le capital social de 100 millions de nairas doit-il être entièrement libéré dès la création, et quelle est la meilleure méthode pour optimiser les droits de timbre?"  
5. "Quelle est la procédure exacte pour obtenir une lettre de 'non-objection' de la CBN pour notre modèle de partenariat spécifique?"  
6. "Comment la récente dissolution du conseil de la protection des consommateurs de Kano affecte-t-elle le processus de plainte pour les e-commerçants?"

## **Synthèse des faits, risques et hypothèses**

| Catégorie | Détails |
| :---- | :---- |
| **Faits confirmés** | La détention directe de fonds nécessite une licence MMO (2Md ₦ capital).3 Le BVN/NIN est obligatoire pour tous les utilisateurs.14 La filiale étrangère nécessite un capital de 100M ₦.34 |
| **Hypothèses** | Le régulateur pourrait tolérer un modèle d'escrow sans licence si les fonds transitent par un compte fiduciaire bancaire géré par API.5 La France sera probablement jugée "adéquate" pour le transfert de données, mais le processus est en cours.33 |
| **Risques critiques** | Requalification de l'activité en banque sans licence si les fonds touchent le compte de la startup.3 Amendes lourdes pour transfert de données non encadré vers l'étranger.32 Conflits de juridiction entre tribunaux civils et Charia à Kano.24 |
| **Recommandations** | Utiliser exclusivement des partenaires bancaires licenciés pour la garde des fonds. Intégrer un co-fondateur nigérian (33 %+) pour bénéficier du Startup Act. Traduire toute la conformité en Haoussa. |

Cette analyse démontre que si le Nigeria offre un marché dynamique pour le commerce social, la barrière à l'entrée est réglementaire et capitalistique. Une approche par étapes, privilégiant les partenariats stratégiques avec des institutions établies et une conformité rigoureuse aux normes de protection des données, est la seule voie viable pour AmanaTrade en phase de MVP.

#### **Sources des citations**

1. Nigeria-Payment-System-2025.pdf \- Nairametrics, consulté le mai 5, 2026, [https://nairametrics.com/wp-content/uploads/2023/01/Nigeria-Payment-System-2025.pdf](https://nairametrics.com/wp-content/uploads/2023/01/Nigeria-Payment-System-2025.pdf)  
2. PSV2025 | Central Bank of Nigeria, consulté le mai 5, 2026, [https://www.cbn.gov.ng/PaymentsSystem/PSV2025.html](https://www.cbn.gov.ng/PaymentsSystem/PSV2025.html)  
3. Licensing Requirements for Fintech Startups in Nigeria \- Lawzana, consulté le mai 5, 2026, [https://lawzana.com/articles/nigeria/licensing-requirements-for-fintech-startups-in-nigeria-960](https://lawzana.com/articles/nigeria/licensing-requirements-for-fintech-startups-in-nigeria-960)  
4. SSKÖHN NOTES \- SSKOHN, consulté le mai 5, 2026, [https://sskohn.com/wp-content/uploads/2022/06/SSKOHN-NOTES\_CBNS-NEW-LICENCE-REQUIREMENTS-FOR-PAYMENTS-SERVICES\_WHAT-YOU-SHOULD-KNOW-1.pdf](https://sskohn.com/wp-content/uploads/2022/06/SSKOHN-NOTES_CBNS-NEW-LICENCE-REQUIREMENTS-FOR-PAYMENTS-SERVICES_WHAT-YOU-SHOULD-KNOW-1.pdf)  
5. THE EMERGENCE OF ESCROW PAYMENTS IN E-COMMERCE ..., consulté le mai 5, 2026, [https://pavestoneslegal.com/the-emergence-of-escrow-payments-in-e-commerce-transactions-in-nigeria/](https://pavestoneslegal.com/the-emergence-of-escrow-payments-in-e-commerce-transactions-in-nigeria/)  
6. Licensing Regime for Payments Sector in Nigeria \- DOA Law, consulté le mai 5, 2026, [https://www.doa-law.com/wp-content/uploads/2021/05/CBN%20New%20License%20Newsletter%20(28052021).pdf](https://www.doa-law.com/wp-content/uploads/2021/05/CBN%20New%20License%20Newsletter%20\(28052021\).pdf)  
7. Licensing for FinTech Startups in Emerging Markets \- Lucid.now, consulté le mai 5, 2026, [https://www.lucid.now/blog/licensing-fintech-startups-emerging-markets/](https://www.lucid.now/blog/licensing-fintech-startups-emerging-markets/)  
8. Legal Requirements For Starting A Fintech Company In Nigeria \- Classic Attorneys, consulté le mai 5, 2026, [https://classic-attorneys.com/legal-requirements-for-starting-a-fintech-company-in-nigeria/](https://classic-attorneys.com/legal-requirements-for-starting-a-fintech-company-in-nigeria/)  
9. CBN Issues New Directives to Payment Service Providers on Routing POS Transactions, consulté le mai 5, 2026, [https://www.aluko-oyebode.com/insights/cbn-issues-new-directives-to-payment-service-providers-on-routing-pos-transactions/](https://www.aluko-oyebode.com/insights/cbn-issues-new-directives-to-payment-service-providers-on-routing-pos-transactions/)  
10. Payment facilitator vs. payment aggregator: How they're different and how to choose one, consulté le mai 5, 2026, [https://stripe.com/ae/resources/more/payment-facilitator-vs-payment-aggregator-how-they-are-different-and-how-to-choose-one](https://stripe.com/ae/resources/more/payment-facilitator-vs-payment-aggregator-how-they-are-different-and-how-to-choose-one)  
11. LICENSING IN NIGERIA'S FINTECH INDUSTRY: UNDERSTANDING THE CBN'S FRAMEWORK. \- Manifield Solicitors, consulté le mai 5, 2026, [https://manifieldsolicitors.com/licensing-in-nigerias-fintech-industry-understanding-the-cbns-framework/](https://manifieldsolicitors.com/licensing-in-nigerias-fintech-industry-understanding-the-cbns-framework/)  
12. Nigeria Mobile Money License – CBN Approval for Payment Services \- Prifinance, consulté le mai 5, 2026, [https://prifinance.com/en/payments/nigeria-emi-license/](https://prifinance.com/en/payments/nigeria-emi-license/)  
13. KYC Requirements for Onboarding New Customers ... \- TMT Thursday, consulté le mai 5, 2026, [https://www.doa-law.com/wp-content/uploads/2024/06/KYC-Requirements-for-Onboarding-New-Customers-for-FinTechs.pdf](https://www.doa-law.com/wp-content/uploads/2024/06/KYC-Requirements-for-Onboarding-New-Customers-for-FinTechs.pdf)  
14. april 2024 \- Inclusion for All Initiative, consulté le mai 5, 2026, [https://inclusion-for-all.org/wp-content/uploads/2024/01/04-SnapshotDec2023-2-2.pdf](https://inclusion-for-all.org/wp-content/uploads/2024/01/04-SnapshotDec2023-2-2.pdf)  
15. BVN | Central Bank of Nigeria, consulté le mai 5, 2026, [https://www.cbn.gov.ng/PaymentsSystem/BVN.html](https://www.cbn.gov.ng/PaymentsSystem/BVN.html)  
16. CBN KYC/AML Requirements 2026: Full Compliance Guide \- Youverify, consulté le mai 5, 2026, [https://youverify.co/blog/cbn-kyc-aml-requirements-2026](https://youverify.co/blog/cbn-kyc-aml-requirements-2026)  
17. Best Practices To Ensure Fintech Compliance in Africa \- DEV Community, consulté le mai 5, 2026, [https://dev.to/flutterwaveeng/best-practices-to-ensure-fintech-compliance-in-africa-48a3](https://dev.to/flutterwaveeng/best-practices-to-ensure-fintech-compliance-in-africa-48a3)  
18. Legal Challenges of E-commerce Disputes in Nigeria: Consumer Rights and Seller Liabilities \- Manifield Solicitors, consulté le mai 5, 2026, [https://manifieldsolicitors.com/legal-challenges-of-e-commerce-disputes-in-nigeria-consumer-rights-and-seller-liabilities/](https://manifieldsolicitors.com/legal-challenges-of-e-commerce-disputes-in-nigeria-consumer-rights-and-seller-liabilities/)  
19. RELEASE: FCCPC Shuts 5 Textile Warehouses in Kano \- Federal Competition & Consumer Protection Commission, consulté le mai 5, 2026, [https://fccpc.gov.ng/release-fccpc-shuts-5-textile-warehouses-in-kano/](https://fccpc.gov.ng/release-fccpc-shuts-5-textile-warehouses-in-kano/)  
20. Kano govt establishes commission to fight market exploitation, price hikes, consulté le mai 5, 2026, [https://dailypost.ng/2025/02/08/kano-govt-establishes-commission-to-fight-market-exploitation-price-hikes/](https://dailypost.ng/2025/02/08/kano-govt-establishes-commission-to-fight-market-exploitation-price-hikes/)  
21. Gov. Yusuf Approves Composition of Kano Consumer Protection Council, consulté le mai 5, 2026, [https://ruraldevelopment.kn.gov.ng/2025/02/08/gov-yusuf-approves-composition-of-kano-consumer-protection-council/](https://ruraldevelopment.kn.gov.ng/2025/02/08/gov-yusuf-approves-composition-of-kano-consumer-protection-council/)  
22. The 10 best E-commerce & Internet Law Lawyers in Kano, Nigeria (2026) \- Lawzana, consulté le mai 5, 2026, [https://lawzana.com/ecommerce-internet-law-lawyers/kano-kano-state](https://lawzana.com/ecommerce-internet-law-lawyers/kano-kano-state)  
23. nji.gov.ng, consulté le mai 5, 2026, [https://nji.gov.ng/assets/publication/Jurisdictional-Issues-in-the-Application-of-Sharia-in-Nigeria-1.docx](https://nji.gov.ng/assets/publication/Jurisdictional-Issues-in-the-Application-of-Sharia-in-Nigeria-1.docx)  
24. (PDF) JURISDICTIONAL CONFLICTS BETWEEN SHARIAH COURTS AND COMMON LAW COURTS IN THE APPLICATION OF ISLAMIC BANKING AND FINANCE IN NIGERIA \- ResearchGate, consulté le mai 5, 2026, [https://www.researchgate.net/publication/327382974\_JURISDICTIONAL\_CONFLICTS\_BETWEEN\_SHARIAH\_COURTS\_AND\_COMMON\_LAW\_COURTS\_IN\_THE\_APPLICATION\_OF\_ISLAMIC\_BANKING\_AND\_FINANCE\_IN\_NIGERIA](https://www.researchgate.net/publication/327382974_JURISDICTIONAL_CONFLICTS_BETWEEN_SHARIAH_COURTS_AND_COMMON_LAW_COURTS_IN_THE_APPLICATION_OF_ISLAMIC_BANKING_AND_FINANCE_IN_NIGERIA)  
25. Disputes Relating to the Appointment of Imams in Nigeria: Jurisdictional Competition Between Islamic Courts and the High Court | Journal of African Law \- Cambridge University Press & Assessment, consulté le mai 5, 2026, [https://www.cambridge.org/core/journals/journal-of-african-law/article/disputes-relating-to-the-appointment-of-imams-in-nigeria-jurisdictional-competition-between-islamic-courts-and-the-high-court/999D42FD8D86B477B8610315A072DB58](https://www.cambridge.org/core/journals/journal-of-african-law/article/disputes-relating-to-the-appointment-of-imams-in-nigeria-jurisdictional-competition-between-islamic-courts-and-the-high-court/999D42FD8D86B477B8610315A072DB58)  
26. Understanding the Nigeria Data Protection Act, 2023 (NDPA) \- Cookie Script, consulté le mai 5, 2026, [https://cookie-script.com/privacy-laws/nigeria-data-protection-act-2023](https://cookie-script.com/privacy-laws/nigeria-data-protection-act-2023)  
27. The Nigeria Data Protection Act, 2023 \- KPMG agentic corporate services, consulté le mai 5, 2026, [https://assets.kpmg.com/content/dam/kpmg/ng/pdf/the-nigeria-data-protection-act-2023.pdf](https://assets.kpmg.com/content/dam/kpmg/ng/pdf/the-nigeria-data-protection-act-2023.pdf)  
28. GUIDANCE NOTICE REGISTRATION OF DATA CONTROLLERS ..., consulté le mai 5, 2026, [https://ndpc.gov.ng/wp-content/uploads/2025/07/Updated-Guidance-Notice-on-Registtration-2024.pdf](https://ndpc.gov.ng/wp-content/uploads/2025/07/Updated-Guidance-Notice-on-Registtration-2024.pdf)  
29. Nigeria Data Protection Commission's Guidance Notice on Registration of Data Processors/ Controllers of Major Importance. \- KPMG agentic corporate services, consulté le mai 5, 2026, [https://assets.kpmg.com/content/dam/kpmg/ng/pdf/2024/03/Nigeria%20Data%20Protection%20Commission%E2%80%99s%20Guidance%20Notice%20on%20Registration%20of%20Data%20ProcessorsControllers%20of%20Major%20Importance.pdf](https://assets.kpmg.com/content/dam/kpmg/ng/pdf/2024/03/Nigeria%20Data%20Protection%20Commission%E2%80%99s%20Guidance%20Notice%20on%20Registration%20of%20Data%20ProcessorsControllers%20of%20Major%20Importance.pdf)  
30. Nigeria Data Protection Act (NDPA) 2023 \- Global Compliance Map, consulté le mai 5, 2026, [https://globalcompliancemap.com/regulation/nigeria-ndpa-2023](https://globalcompliancemap.com/regulation/nigeria-ndpa-2023)  
31. Data protection laws in Nigeria, consulté le mai 5, 2026, [https://www.dlapiperdataprotection.com/index.html?t=law\&c=NG](https://www.dlapiperdataprotection.com/index.html?t=law&c=NG)  
32. Moving Personal Data Across Borders? What Your Startup Needs to Know, consulté le mai 5, 2026, [https://topeadebayolp.com/moving-personal-data-across-borders-what-your-startup-needs-to-know/](https://topeadebayolp.com/moving-personal-data-across-borders-what-your-startup-needs-to-know/)  
33. Article 7: Cross-Border Data Transfers \- Osuntuyi & Tokan-Lawal Law, consulté le mai 5, 2026, [https://otllaw.com/article-7-cross-border-data-transfers/](https://otllaw.com/article-7-cross-border-data-transfers/)  
34. How to Register a Company with Foreign Participation with the Corporate Affairs Commission in Nigeria \- Kabbiz Global Nominees Limited, consulté le mai 5, 2026, [https://www.kabbizglobal.com/how-to-register-company-with-foreign-participation-in-nigeria-with-cac/](https://www.kabbizglobal.com/how-to-register-company-with-foreign-participation-in-nigeria-with-cac/)  
35. Foreign Participation in Nigerian Business \- PUKKA Logistics and Support Services Ltd, consulté le mai 5, 2026, [https://pukkalogistics.com.ng/foreign-participation-in-nigerian-business/](https://pukkalogistics.com.ng/foreign-participation-in-nigerian-business/)  
36. Incorporating a Foreign-Owned Tech Startup in Nigeria \- Lawzana, consulté le mai 5, 2026, [https://lawzana.com/articles/nigeria/incorporating-a-foreign-owned-tech-startup-in-nigeria-1224](https://lawzana.com/articles/nigeria/incorporating-a-foreign-owned-tech-startup-in-nigeria-1224)  
37. Capital Repatriation in Nigeria \- Foreign Investor Guide \- Lawzana, consulté le mai 5, 2026, [https://lawzana.com/articles/nigeria/capital-repatriation-in-nigeria-foreign-investor-guide-1187](https://lawzana.com/articles/nigeria/capital-repatriation-in-nigeria-foreign-investor-guide-1187)  
38. How to Successfully Repatriate Capital and Profits in Nigeria by Foreign Investors, consulté le mai 5, 2026, [https://www.adeolaoyinlade.com/en/how-to-successfully-repatriate-capital-and-profits-in-nigeria-by-foreign-investors/](https://www.adeolaoyinlade.com/en/how-to-successfully-repatriate-capital-and-profits-in-nigeria-by-foreign-investors/)  
39. REPATRIATION OF FUNDS AND CAPITAL IMPORTATION IN NIGERIA \- FAQs | TEMPLARS Law, consulté le mai 5, 2026, [https://www.templars-law.com/app/uploads/2020/06/Templars-Thought-Leadership-Repatriation-of-Funds-and-Capital-Importation-in-Nigeria-FAQs.pdf](https://www.templars-law.com/app/uploads/2020/06/Templars-Thought-Leadership-Repatriation-of-Funds-and-Capital-Importation-in-Nigeria-FAQs.pdf)  
40. INFORMATION CIRCULAR ON THE CLAIM OF TAX TREATIES BENEFITS IN NIGERIA \- KPMG agentic corporate services, consulté le mai 5, 2026, [https://assets.kpmg.com/content/dam/kpmg/ng/pdf/tax/information-circular-on-the-claim-of-tax-treaties-benefits-in-nigeria.pdf](https://assets.kpmg.com/content/dam/kpmg/ng/pdf/tax/information-circular-on-the-claim-of-tax-treaties-benefits-in-nigeria.pdf)  
41. FIRS terminates uniform WHT rate for residents of treaty countries \- KPMG International, consulté le mai 5, 2026, [https://assets.kpmg.com/content/dam/kpmg/ng/pdf/tax/firs-terminates-uniform-wht-rate-for-residents-of-treaty-countries.pdf](https://assets.kpmg.com/content/dam/kpmg/ng/pdf/tax/firs-terminates-uniform-wht-rate-for-residents-of-treaty-countries.pdf)  
42. Notice on Changes to the Double Tax Treaty Regime on Foreign Listing of Securities \- G Elias, consulté le mai 5, 2026, [https://www.gelias.com/images/Notice\_on\_Changes\_to\_the\_Double\_Tax\_Treaty\_Regime\_on\_Foreign\_Listing\_of\_Securities.pdf](https://www.gelias.com/images/Notice_on_Changes_to_the_Double_Tax_Treaty_Regime_on_Foreign_Listing_of_Securities.pdf)  
43. Nigeria \- Corporate \- Withholding taxes \- Worldwide Tax Summaries \- PwC, consulté le mai 5, 2026, [https://taxsummaries.pwc.com/nigeria/corporate/withholding-taxes](https://taxsummaries.pwc.com/nigeria/corporate/withholding-taxes)  
44. Nigeria Modernizes Tax Collection | Global Finance Magazine, consulté le mai 5, 2026, [https://gfmag.com/economics-policy-regulation/nigeria-modernizes-tax-collection/](https://gfmag.com/economics-policy-regulation/nigeria-modernizes-tax-collection/)  
45. Nigeria signs tax data MoU with France, raising sovereignty concerns, consulté le mai 5, 2026, [https://africa.businessinsider.com/local/lifestyle/nigeria-signs-tax-data-mou-with-france-raising-sovereignty-concerns/db2qdg7](https://africa.businessinsider.com/local/lifestyle/nigeria-signs-tax-data-mou-with-france-raising-sovereignty-concerns/db2qdg7)  
46. Obtaining a Startup Label Under the Nigeria Startup Act, 2022 \- Balogun Harold, consulté le mai 5, 2026, [https://www.balogunharold.com/insights/obtaining-a-startup-label-under-the-nigeria-startup-act-2022](https://www.balogunharold.com/insights/obtaining-a-startup-label-under-the-nigeria-startup-act-2022)  
47. NIGERIA STARTUP ACT, 2022 \- UHY Maaji & Co, consulté le mai 5, 2026, [https://uhy-ng-maaji.com/wp-content/uploads/2023/10/THE-NIGERIA-STARTUP-ACT-2022.pdf](https://uhy-ng-maaji.com/wp-content/uploads/2023/10/THE-NIGERIA-STARTUP-ACT-2022.pdf)  
48. Key Provisions of the Nigeria Start-Up Act 2022 Every Tech Founder Should Know., consulté le mai 5, 2026, [https://aeolawpractice.wordpress.com/2024/12/05/key-provisions-of-nigerias-start-up-act-2022-every-tech-founder-should-know/](https://aeolawpractice.wordpress.com/2024/12/05/key-provisions-of-nigerias-start-up-act-2022-every-tech-founder-should-know/)  
49. Nigeria Startup Act Implementation: Establishment of the Nigeria Startup Support and Engaement Portal | Acelera Law, consulté le mai 5, 2026, [https://www.acelera.law/publications/nigeria-startup-act-implementation-establishment-of-the-nigeria-startup-support-and-engaement-portal](https://www.acelera.law/publications/nigeria-startup-act-implementation-establishment-of-the-nigeria-startup-support-and-engaement-portal)  
50. Payment Service Providers | Central Bank of Nigeria, consulté le mai 5, 2026, [https://www.cbn.gov.ng/PaymentsSystem/PSPs.html](https://www.cbn.gov.ng/PaymentsSystem/PSPs.html)  
51. guidelines on shariah governance for non-interest financial \- Central Bank of Nigeria, consulté le mai 5, 2026, [https://www.cbn.gov.ng/OUT/2011/CIRCULARS/FPR/FINAL%20GUIDELINES%20ON%20SHARIAH%20GOVERNANCE.PDF](https://www.cbn.gov.ng/OUT/2011/CIRCULARS/FPR/FINAL%20GUIDELINES%20ON%20SHARIAH%20GOVERNANCE.PDF)  
52. Vol. 33\. No. 6\. November Issue (2024) REGULATING ISLAMIC P2P FINANCING IN NIGERIA: A CASE FOR A COMPLIANCE FRAMEWORK \- al-Qanatir, consulté le mai 5, 2026, [http://al-qanatir.com/aq/article/download/953/709](http://al-qanatir.com/aq/article/download/953/709)