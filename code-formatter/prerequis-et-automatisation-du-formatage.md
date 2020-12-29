# Prérequis et automatisation du formatage

## Prérequis pour la mise en place de formatage de code

Il y a différents prérequis \(**évident**\) à mettre en place et à respecter pour qu'un outil de formatage de code fasse sa tache correctement. Cela passe par l'explication de l'utilité du formatage de code et par l'automatisation de l'installation, ainsi que l'intégration du formatage dans le processus \(workflow\) de publication du code.

### 1er : Tous le monde doit l'installer. 

Pour cela, une installation manuel avec un tuto OU une installation automatique lors de l'installation des dépendance du projet, par exemple.

Par exemple, une fois l'installation configuré dans le projet, Prettier est installé par npm pour tous les développeurs, comme une dépendance du projet.

### 2nd : Tous le monde doit l'utiliser

Si l'outil de formatage est installé mais qu'il n'est pas utilisé, parce que l'on oublie, parce qu'on ne sais pas quand le lancer dans le workflow, parce qu'on n'aime pas le formatage \(\#schtroumpf\_grognon 😠\)

alors tous le code n'est pas entièrement formaté de manière cohérente.

### configure l'outil dans l'IDE

* avoir la configuration de l'outil commune, partagé entre tous les dev

## Automatiser le formatage de code

fichier est modifié et que les modifications sont enregistrées automatiquement ou manuellement.

formater a la sauvegarde des fichiers.

formater au pre-commit

a un autre moment avant le partage du code



