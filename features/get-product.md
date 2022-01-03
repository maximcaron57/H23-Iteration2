[← Back](../README.md)

# Obtention produit

## Description

En tant qu'utilisateur, je peux accéder aux informations d'un produit.

## Critères de succès

- Je vois les informations de base du vendeur.
- Je vois quelques statistiques sur les offres.
- La moyenne des montants des offres est `null` s'il n'y a pas d'offres.

## Détails techniques

### Requête

**Route**

`GET /products/{productId}`

### Réponse

**Status**

`200 OK`

**Body**

```ts
{
  id: string,
  createdAt: DateTime,
  title: string,
  description: string,
  suggestedPrice: Amount,
  category: ProductCategory,
  seller: {
    id: string,
    name: string,
  },
  offers: {
    count: number,
    avgAmount: Amount | null,
  }
}
```

**Exemple : avec offres**

```json
{
  "id": "123",
  "createdAt": "2020-06-30T23:54:23.382Z",
  "title": "Nice hairbrush",
  "description": "Pink and all.",
  "suggestedPrice": 34.21,
  "category": "beauty",
  "seller": {
    "id": "abc",
    "name": "John Doe",
  },
  "offers": {
    "count": 2,
    "avgAmount": 36.43
  }
}
```

**Exemple : sans offre**

```json
{
  "id": "123",
  "createdAt": "2020-06-30T23:54:23.382Z",
  "title": "Nice hairbrush",
  "description": "Pink and all.",
  "suggestedPrice": 34.21,
  "category": "beauty",
  "seller": {
    "id": "abc",
    "name": "John Doe",
  },
  "offers": {
    "count": 0,
  }
}
```

### Exceptions

- `ITEM_NOT_FOUND` si le produit associé à `productId` n'existe pas.
