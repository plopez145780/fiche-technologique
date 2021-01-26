---
description: Réappliquer les commits à partir un autre commit de départ
---

# Rebase

##  Définition

Comme son nom l'indique, **rebase** est là pour changer la « base » d'une branche, **c'est**-à-dire son point de départ. Elle rejoue une série de commits à partir d'une nouvelle base de travail.

Pour cela, il faut réecrire l'historique de commit de git.

## Cas d'utilisation

Je vois deux grands cas d'utilisation de rebase.

### Mettre son développement à la suite de master

C'est à dire prendre toutes les modifications qui ont été validées sur sa branche et les rejouer en repartant de master. De cette façon, le code de developpement commence à partir d'un master mis à jour.

Variante : prendre toutes les modifications qui ont été validées sur une branche et les rejouer sur une autre.

Mettre a jour sa branche avec la branche master distante : `git rebase origin/master`

\("origin/master" est la reférence vers le master distant de gitlab\)

#### Fonctionnement

1. git recherche de l’ancêtre commun le plus récent des deux branches. \(exemple : master et feature1\)
2. git récupére toutes les différences introduites par chaque _commit_ de la branche courante \(feature1\)
3. git sauvegarde les différences dans des fichiers temporaires
4. git réinitialise la branche courante sur le même _commit_ que la branche de destination \(master\)
5. git réapplique les sauvegardes dans le même ordre.

Résultat les commits de feature1 sont à la suite de tous les comits de master.

#### Pourquoi utiliser le rebase "manuel"

Cela évite les surprises plus tard au moment de la fusion avec master. La gestion des conflits est géré en local au moment du rebase, et non pas à distance.

Cela permet d'avoir un joli historique, c'est à dire un historique linéaire et simple à relire \(important lorsqu'on a vraiment besoin de lire l'historique\)

### Réorganiser ces commits avant push

Réorganiser les commits créer lors de son développement avant de les partager avec l'équipe permet de nettoyer un historique désordonné avant de fusionner sa branche dans master.

 rebase interactif : `git rebase -i <nouvelle-base>`

Le mode interractif permet de spécifier à git comment organiser les nouveaux commits.

* **pick**, permet d'inclure le commit. On peut en profiter pour changer l'ordre des différents commit
* **reword**, permet d'inclure le commit tout en ayant la possibiliter de changer le message
* **edit**, permet d'éditer le commit. En séparant en plusieurs commits par exemple
* **squash**, regroupement de plusieurs commits. Combine le commit avec le commit du dessus et permet de changer le message du commit
* **fixup**, comme **squash** mais utilisera le message du commit situé au dessus
* **exec**, permet de lancer des commandes shell sur le commit
* **break**, pause \(un 'git rebase --continue' est nécessaire pour continuer\)
* **drop**, supprime le commit
* **label**  = label current HEAD with a name
* **reset**  = reset HEAD to a label
* **merge** \[-C  \| -c \]  \[\# \] . create a merge commit using the original merge commit's . message \(or the oneline, if no original merge commit was . specified\). Use -c  to reword the commit message.

Les lignes peuvent être réordonnées \(exécutés de haut en bas\)

Si une ligne est supprimé ou mise en commentaire, le commit ne sera pas réappliqué et donc il sera perdu.







## Rebase avancé "--onto"

L'option --onto permet de spécifié  2 branches pour recupérer les commits supplémentaire entre les 2, pour les appliquer sur une 3eme branche.

### Exemple

`git rebase --onto master serveur client`

Cela signifie "Extraire la branche client, déterminer les commits depuis l’ancêtre commun des branches `client` et `serveur` puis les rejouer sur `master` "

## Les dangers du rebase

Ne jamais rebaser l'historique public, réécrit l'historique de git s'il a été partagé car les commit existant sont supprimé et de nouveaux sont créé. Cela va créer des conflits pour les autres utisateurs ou supprimer le travail d'autre personne.

JAMAIS DE REBASE DE MASTER

Le rebase est à faire que si l'on est seul sur la branche. Cela oblige d'écraser et donc détruire l'ancien historique distant à chaque push. `git push --force`

## En cas de panique

Annuler le rebase et revenir a l'état avant le debut du rebase : `git rebase --abort`

J'ai finit le rebase et ce n'est pas bon, tous est cassé !

Grace à reflog vous pouvez retrouver le hash du commit avant le rebase et retirer une branche

```text
git reflog
git checkout -b nouvelle_branche hash_commit
```

## Sources

{% embed url="https://git-scm.com/docs/git-rebase" %}

{% embed url="https://git-scm.com/book/fr/v2/Les-branches-avec-Git-Rebaser-Rebasing" %}

{% embed url="https://www.atlassian.com/fr/git/tutorials/rewriting-history/git-rebase" %}

{% embed url="https://www.miximum.fr/blog/git-rebase/" %}

{% embed url="https://www.grafikart.fr/tutoriels/amend-rebase-588" %}



