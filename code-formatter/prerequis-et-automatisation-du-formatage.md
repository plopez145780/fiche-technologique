# Prérequis et automatisation du formatage

## Prérequis pour la mise en place de formatage de code

Il y a différents prérequis \(**évident**\) à mettre en place et à respecter pour qu'un outil de formatage de code fasse sa tache correctement. Cela passe par l'explication de l'utilité du formatage de code et par l'automatisation de l'installation, ainsi que l'intégration du formatage dans le processus \(workflow\) de publication du code.

### 1er : Tous le monde doit l'installer. 

Pour cela, une installation manuel avec un tuto OU une installation automatique.

* Installation via le plugin à rechercher dans le marché d'extension de l'IDE.
* Installation manuel via npm globalement ou pour le projet seulement.
* Installation automatique au téléchargement des dépendances par une configuration comme une dépendance du projet.

Tous ca pour dire, il faut penser à comment installé l'outil de la façon la plus simple et transparente.

Attention, un effet de bord de certaine manière d'installer l'outil est que tous le monde ai l'outil mais dans des versions différentes.

### 2nd : Tous le monde doit l'utiliser

Si l'outil de formatage est installé mais qu'il n'est pas utilisé, ca ne sert a rien, tous le code n'est pas entièrement formaté de manière cohérente.

Les raisons de la non utilisation peuvent être : 

* on oublie de l'exécuter manuellement
* on ne sais pas quand le lancer dans le workflow de développement
* on n'aime pas le formatage de l'outil \(\#schtroumpf\_grognon 😠\)
* ou tous simplement car il n'est pas configuré.

Il faut avoir un minimum de documentation pour expliquer l'intérêt du formatage de code pour le projet et comment utiliser l'outil.

## 3eme : La configuration

Je vois deux types de configuration :

* La configuration au sein de l'outil : les règles de formatages
* La configuration pour le lancement de l'outil : l'automatisation du processus de formatage

### Pour la configuration des règles

Il faut avoir un fichier de configuration versionné au sein du projet, afin que la configuration de l'outil soit commune, et partagé entre tous les dev de la façon la plus simple.



En revanche, il me semble utile de mettre en place une vérification manuel par la personne qui installe pour vérifier que l'outil fonctionne en utilisant la configuration du fichier.

## Automatiser le formatage de code



config de l'IDE : prettier peux être installé dans l'ide et configurer, et utiliser 'formatage a la sauvegarde', ave le plugin dans l'ide

fichier est modifié et que les modifications sont enregistrées automatiquement ou manuellement.

formater a la sauvegarde des fichiers.



formater au pre-commit



a un autre moment avant le partage du code



