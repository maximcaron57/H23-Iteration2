[← Back](../README.md)

# Création offre

## Description

En tant qu'acheteur, je peux faire une offre sur un produit afin de montrer qu'il m'intéresse.

## Critères de succès

- Le montant minimal est le montant suggéré du produit.
- Le message est d'au moins 100 caractères.
- Un acheteur peut faire seulement 1 offre par produit.
- La nouvelle offre possède une date de création non-modifiable.
- La nouvelle offre est sauvegardée dans l'application.

## Détails techniques

### Requête

**Route**

`POST /products/{productId}/offers`

**Headers**

- `X-Buyer-Username` : Nom d'utilisateur de l'acheteur qui créer l'offre
  - type: `string`

**Body**

```ts
{
  amount: Amount,
  message: string,
}
```

**Exemple**

```json
{
    "amount": 12.33,
    "message": "I need these because...+100",
}
```

### Réponse

**Status**

`201 CREATED`

### Exceptions

- `MISSING_PARAMETER` si un champ de la requête est manquant.
- `INVALID_PARAMETER` si un des champs de la requête est invalide.
- `NOT_PERMITTED` si une offre de l'acheteur existe déjà sur le produit.
- `ITEM_NOT_FOUND` si le produit associé à `productId` n'existe pas.
