---
description: Code formatter - Outil de formatage de code.
---

# Code formatter

## Qu'est ce qu'un code formatter ?

C'est un outil qui permet de reformatter le code en appliquant des conventions de style de code bien définit \(les règles prédéfinis dans l'outil\).

Cela consiste généralement à réindenter les lignes, gérer les espace entre les mots, gérer les retours à la ligne, gérer les guillemets simple ou double, optimiser les import, …

## Comment ca fonctionne ?

Un outil de formatage de code \(ici Prettier\) analyse le code source du langage cible avec un AST parser \(Abstract Syntax Tree parser\) et ensuite re-imprimer dans le fichier le code sans tenir compte du formatage précédent.

{% embed url="https://fr.wikipedia.org/wiki/Arbre\_de\_la\_syntaxe\_abstraite" %}

## Intérêt

### Quel est l'intérêt d'utiliser un outil de formatage de code ?

* Le code est plus jolie. :\)
* Le code est formatté de manière homogène pour tous le monde.
* Le code est plus lisible. \(donc plus facilement lisible et du coup plus maintenable\)

### Quel est l'intérêt d'utiliser un outil de formatage de code tiers ?

Généralement un outil de formatage de code est inclus dans les IDE, mais ce n'est pas forcement le même d'un IDE à l'autre. Il peut être intéressant d'utiliser un outil  externe pour gérer la formatage indépendamment de l'IDE, lors que les développeurs utilise différents IDE.

Un outil de formatage peut avoir une philosophie différentes de l'outil intégré dans l'IDE, et ainsi ajouter des règles/contraintes supplémentaire.

## Outils de formatage de code

On trouve sur le marché d'extension de VS Code différent plugins pour tous les langages.

{% embed url="https://marketplace.visualstudio.com/search?target=VSCode&category=Formatters&sortBy=Installs" %}

Par exemple, il y a Prettier et BeautifyJs de très connue.



