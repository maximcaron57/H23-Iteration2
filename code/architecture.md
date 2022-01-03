[← Back](../README.md)

# Requis architecturaux

## Respect des couches

Durant le laboratoire 4, vous avez appris les bienfaits d'avoir une architecture séparée en couche, dont notamment avoir la couche présentative (API/UI/GUI/etc.) séparée de la couche logique (domaine). Vous devrez donc vous assurez de respecter les critères d'une telle architecture.

## Responsabilité des classes

En lien avec clean code, vous avez appris les différents problèmes reliés à des classes qui en font trop (trop grosses, trop d'actions, trop de données, etc.). Vous devez donc appliquer le Principe de Single Reponsibility (SRP), c'est-à-dire vous assurez qu'une classe/méthode n'aie qu'"une seule raison de changer", ou plus précisément n'effectue pas plus qu'une tâche. Ainsi, vous devez séparer vos différentes logiques et algorithmes en différentes classes uniques, testables séparément (par exemple, la transformation des données entre le domaine et la couche de présentation).

## Packages

Afin de bien séparer ces classes, on vous demande également de choisir une **structure de packages**. Pour ce faire, recherchez des stratégies existantes sur le Web. On parle souvent de "vertical slicing vs. horizontal slicing". Quelques degrés de séparations inclus :

- couches (api, domaine, etc.)
- modules (seller, product, etc.)
- type (requests, assemblers, etc.)

Certaines séparations sont plus adaptées à votre projet et permettre d'évoluer plus facilement. Assurez-vous de bien faire vos recherches et d'en discutter en équipe!

## Diagrammes (NOUVEAU)

Afin de bien visualiser les dépendances entre vos classes et vos couches, vous devez fournir un diagramme d'architecture simplifié. Pour ce faire, voici quelques directives :

- Pas besoin des méthodes ni des attributs, seulement besoin des **noms des classes**
- Pas besoin des classes de type value-object (ex: `Email`, `PhoneNumber`, `SellerId`, etc.) sauf si vraiment pertinent
- N'inclure **aucune** classe que vous **n'avez pas crées** (ex: les classes de la librairie standard ou de Jakarta)
- Reliez chaque classe aux autres classes avec une flèches si cette classe **utilise** (*uses*), **reçoit** (*receives*), **créer** (*creates*), **trouve/sauvegarde** (*finds/saves*), **se transforme en** (*maps to*), **valide** (*validates*), **modifie** (*modifies*), **implémente** (*implements*) etc. cette autre classe (pensez aux actions générale et non pas aux actions spécifiques comme "modifie le nom")
- Indiquez clairement la **couche** d'appartenance de chaque classe (ex: à l'aide de couleurs et d'une légende)

Vous devez également, dans un cours texte associé :

- Décrire les rôles des classes principales
- Expliquer vos choix
- Noter les endroits où les relations semblent suspectes et trouver des solutions potentielles

Autres conseils:

- Pas d'annotations UML, seulement des flèches et des boîtes de base
- Pour améliorer la lisibilité, vous pouvez faire 1 diagramme par objet central (`Seller`, `Product`, etc.) ou par action principale ("création produit", "obtention produits", etc.). Par contre, plus vous séparez en petits diagrammes, plus vous cachez les problèmes potentiels de votre architecture.
- Évitez le plus possible les croisements et superpositions
- Exportez votre diagramme en PNG, de qualité suffisante pour être **très** lisible
- Français ou anglais, idéalement pas un mélange des deux
- Outil suggéré : <https://app.diagrams.net> (**pas** Visual Paradigm)

Exemple de diagramme pour une feature très simple de "gestion des utilisateurs" (incomplet) :

<div align="center">
<img src="https://user-images.githubusercontent.com/32545895/218632494-9c417121-49c1-45c1-97a4-427a9450e965.png" width="600px" alt="Diagramme architecture simplifié">
</div>
