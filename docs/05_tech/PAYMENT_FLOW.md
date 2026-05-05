# PAYMENT FLOW — AmanaTrade

## Objectif de ce document
Documenter le flux de paiement et de séquestre étape par étape, en intégrant les contraintes légales, techniques et utilisateur.

---

## Principe
L'argent de l'acheteur est retenu par AmanaTrade (ou son partenaire licencié) jusqu'à confirmation de réception satisfaisante par l'acheteur. Ensuite, le montant moins la commission est libéré au vendeur.

---

## Flux principal — Happy Path

```
[Acheteur]                    [AmanaTrade]                 [Vendeur]
    |                               |                           |
    |-- Initie la transaction ----→ |                           |
    |                               |-- Notifie le vendeur --→  |
    |                               |  ← Vendeur accepte ------ |
    |-- Paie (montant total) -----→ |                           |
    |                               | (Fonds en séquestre)      |
    |  ← Confirmation paiement ---- |                           |
    |                               |-- Notifie expédition --→  |
    |  (Vendeur expédie)            |                           |
    |  ← Notifie livraison -------- |                           |
    |-- Confirme réception ------→  |                           |
    |                               |-- Libère paiement (- commission) → |
    |  ← Confirmation clôture ----- |                           |
```

*Ce diagramme est provisoire — à affiner selon les contraintes légales et techniques.*

---

## Flux alternatifs

### Cas : Acheteur ne confirme pas dans X jours
*À définir — délai automatique de libération ?*

### Cas : Litige ouvert par l'acheteur
*À définir — voir DISPUTE_RESOLUTION_POLICY.md*

### Cas : Vendeur ne confirme pas l'expédition
*À définir*

---

## Questions ouvertes sur le flux
> *À déplacer vers AGENT_QUESTIONS.md*
- Qui détient juridiquement les fonds en séquestre ?
- Quel délai de confirmation avant libération automatique ?
- Comment prouver la livraison dans un contexte informel (pas de tracking) ?

---

*Responsable : Tech Architecture Agent + Legal & Compliance Agent*
*Dépendances : ESCROW_LEGAL_OPTIONS.md, TECH_ARCHITECTURE.md*
