[← Back](../README.md)

# Tests

## Tests unitaires

Afin d'assurer un bon fonctionnement de chaque partie du code, vous devez tester unitairement **toutes les méthodes de toutes vos classes**. Par contre, en pratique, on ne test souvent pas les éléments suivants :

- Les constructeurs (**sauf** pour les validations)
- Les classes de ressources (seront testées dans les e2e)
- Le "contexte" (`Main`, préparation et enregistrement des resources, etc.)
- Les méthodes `get` (sont testées par la bande)

Avoir de pouvoir facilement tester des comportements uniques, vous devrez créer beaucoup plus de classes que simplement celles des resources. Par exemple, pensez à créer des *factories* pour la création (avec validations) des entités, des *repositories* pour la sauvegarde et le *fetching* des entités, ou encore des *assemblers/mappers* pour la convertion des entités en réponses. Le but est de réussir à tester le plus de comportements possibles!

## Clean code

L'ensemble de vos tests doivent respecter les meilleures pratique en matière de Clean Code. Vous devez donc vous assurer de :

- Avoir un naming représentant clairement les 3 étapes du test (arrange / act / assert)
- Avoir un contenu qui représente clairement ces 3 étapes
- Avoir un contenu clair et précis, sans trop de préparation qui viendrait bruité le test
- Découper le code en sous-fonction et sous-classes lorsque nécessaire
- Éviter les "valeurs magiques"
