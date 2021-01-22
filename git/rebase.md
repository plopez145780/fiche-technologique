---
description: Réappliquer les commits à partir un autre commit de départ
---

# Rebase

##  Définition

Comme son nom l'indique, **rebase** est là pour changer la « base » d'une branche, **c'est**-à-dire son point de départ. Elle rejoue une série de commits à partir d'une nouvelle base de travail.

Pour cela, il faut réecrire l'historique de commit de git.

## Cas d'utilisation

Faire partir son code de developpement depuis un master qui a ete mis a jour depuis le debut de son developpement

pourquoi 

pour que notre code part de master et ainsi pour regé les conflits au plus tot et evité les surprise plus tard

pour avoir un jolie historique, c'est a dire un historique linéaire et simple a relire \(lorsqu'on a vraiment besoin de lire l'historique\)





Reorganiser les commit créer lors de sont developpement avant de les partager avec l'equipe.

 le rebase interactif est utilisé pour nettoyer un historique désordonné avant de merger branche de fonctionnalité dans `master`.



Un “squash” est un regroupement de plusieurs commits. Le but est de les fusionner en un seul pour avoir un historique Git plus propre. Il est notamment conseillé de le faire dans le cadre des Pull Request pour simplifier la relecture des modifications effectuées.



donner une base au rebase



pick



cherry-pick



Toute reecriture de l'historique de git 

oblige d'ecrasé et donc detruire d'ancien historique

git push --force

a faire que si l'on est seul sur la branche \(ne pas faire si il y a une partage\)





## Sources

{% embed url="https://git-scm.com/docs/git-rebase" %}

{% embed url="https://git-scm.com/book/fr/v2/Les-branches-avec-Git-Rebaser-Rebasing" %}

{% embed url="https://www.atlassian.com/fr/git/tutorials/rewriting-history/git-rebase" %}

{% embed url="https://www.miximum.fr/blog/git-rebase/" %}

{% embed url="https://delicious-insights.com/fr/articles/bien-utiliser-git-merge-et-rebase/" %}

{% embed url="https://www.grafikart.fr/tutoriels/amend-rebase-588" %}



