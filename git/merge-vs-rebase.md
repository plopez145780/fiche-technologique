---
description: 'Deux méthodes, un même résultat'
---

# Merge VS Rebase

Il n’y a pas de différence entre le code final entre les deux type d'intégration : merge et rebase.

La différence est dans l'historique des commits de git. Le commit final sera soit le dernier des commits d’une opération de rebasage, soit le commit d’une fusion.

## Situation 

Faire un merge entre 2 branche qui ont evolué





Un `git merge` ne devrait être utilisé que pour **la récupération fonctionnelle, intégrale et finale d’une branche dans une autre**, afin de préserver un graphe d’historique sémantiquement cohérent et utile, lequel représente une véritable valeur ajoutée.

Tous les autres cas de figure relèvent du `rebase` sous toutes ses formes : classique, tri-partite, interactif ou _cherry picking_.



### Merge

```text
# Crée un commit 
git checkout feature
git merge master
```

+ non destructive / ne réécrit pas l'historique

-- creation de commit de merge dans la branche-feature \(pollution de l'historique si plusieurs commit de merge\)

commit de merge donne du context, vous pouvez mieux voir à quel moment des changements apportés au dépôt upstream ont été intégrés à la branche de fonctionnalité.

-Le rebase est une méthode courante pour intégrer les changements en amont dans votre dépôt local. L'intégration des changements en amont avec git merge génère un commit de merge superflu dès que vous voulez voir comment le projet a évolué.



### Rebase

```text
# Rebase master au debut de la branche feature
git checkout feature
git rebase master
# Merge en fast-forward de feature dans master
git checkout master
git merge feature
```

- Réécrit l'historique.  
- Demande de respecter des règles strictes à cause de la réecriture de l'historique.  
+ Pas de commit supplémentaire \(commit de merge\)  
+ Les commits de la branches en cours de développement sont toujours à fin \(facilite le fast-forward\).  
+ L'historique est linéaire / "plus propre" / plus lisible.

## Conclusion : Rebaser ou Fusionner

De manière générale, la manière de profiter au mieux des deux mondes consiste à **rebaser des modifications locales** que vous avez effectuées mais qui n’ont pas encore été partagées avant de les pousser de manière à obtenir un historique propre mais sans jamais rebaser quoi que ce soit que vous ayez déjà poussé quelque part.



![](../.gitbook/assets/image%20%282%29.png)



## Source

{% embed url="https://www.atlassian.com/fr/git/tutorials/merging-vs-rebasing" %}

{% embed url="https://delicious-insights.com/fr/articles/bien-utiliser-git-merge-et-rebase/" %}



