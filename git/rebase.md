---
description: Réappliquer les commits à partir un autre commit de départ
---

# Rebase

##  Définition

Comme son nom l'indique, **rebase** est là pour changer la « base » d'une branche, **c'est**-à-dire son point de départ. Elle rejoue une série de commits à partir d'une nouvelle base de travail.

Pour cela, il faut réecrire l'historique de commit de git.

## Fonctionnement

1. git recherche de l’ancêtre commun le plus récent des deux branches. \(exemple : master et feature1\)
2. git récupére toutes les différences introduites par chaque _commit_ de la branche courante \(feature1\)
3. git sauvegarde les différences dans des fichiers temporaires
4. git réinitialise la branche courante sur le même _commit_ que la branche de destination \(master\)
5. git réapplique les sauvegardes dans le même ordre.

Résultat les commits de feature1 sont à la suite de tous les comits de master.

## Cas d'utilisation

Je vois deux grands cas d'utilisation de rebase :

### Mettre son développement à la suite de master

C'est a dire prendre toutes les modifications qui ont été validées sur sa branche et les rejouer en repartant de master. Comme ça, le code de developpement commence à partir d'un master mis à jour.

#### Pourquoi 

pour régler les conflits au plus tot, c'est a dire au moment du rebase sur sa branche local

Cela évite les surprise plus tard au moment de la fusion avec master. La gestion des conflits est géré en local, pas à distance.

pour que notre code part de master et ainsi pour regé les conflits au plus tot et evité les surprise plus tard

pour avoir un jolie historique, c'est a dire un historique linéaire et simple a relire \(lorsqu'on a vraiment besoin de lire l'historique\)







vous pouvez prendre toutes les modifications qui ont été validées sur une branche et les rejouer sur une autre.

#### Pourquoi 

pour que notre code part de master et ainsi pour regé les conflits au plus tot et evité les surprise plus tard

pour avoir un jolie historique, c'est a dire un historique linéaire et simple a relire \(lorsqu'on a vraiment besoin de lire l'historique\)





Reorganiser les commit créer lors de sont developpement avant de les partager avec l'equipe.

 le rebase interactif est utilisé pour nettoyer un historique désordonné avant de merger branche de fonctionnalité dans `master`.



Un “squash” est un regroupement de plusieurs commits. Le but est de les fusionner en un seul pour avoir un historique Git plus propre. Il est notamment conseillé de le faire dans le cadre des Pull Request pour simplifier la relecture des modifications effectuées.



donner une base au rebase



pick



cherry-pick



danger du rebase

Toute reecriture de l'historique de git 

oblige d'ecrasé et donc detruire d'ancien historique

git push --force

a faire que si l'on est seul sur la branche \(ne pas faire si il y a une partage\)

 **Ne rebasez jamais des** _**commits**_ **qui ont déjà été poussés sur un dépôt public.**





## Sources

{% embed url="https://git-scm.com/docs/git-rebase" %}

{% embed url="https://git-scm.com/book/fr/v2/Les-branches-avec-Git-Rebaser-Rebasing" %}

{% embed url="https://www.atlassian.com/fr/git/tutorials/rewriting-history/git-rebase" %}

{% embed url="https://www.miximum.fr/blog/git-rebase/" %}

{% embed url="https://www.grafikart.fr/tutoriels/amend-rebase-588" %}



