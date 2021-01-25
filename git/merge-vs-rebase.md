# Merge VS Rebase

Il n’y a pas de différence entre les résultats des deux types d’intégration, mais rebaser rend l’historique plus clair.



 Il faut noter que l’instantané pointé par le _commit_ final, qu’il soit le dernier des _commits_ d’une opération de rebasage ou le _commit_ final issu d’une fusion, sont en fait le même instantané — c’est juste que l’historique est différent.

 Rebaser rejoue les modifications d’une ligne de _commits_ sur une autre dans l’ordre d’apparition, alors que la fusion joint et fusionne les deux têtes.

## 

## Situation 

Faire un merge entre 2 branche qui ont evolué





Un `git merge` ne devrait être utilisé que pour **la récupération fonctionnelle, intégrale et finale d’une branche dans une autre**, afin de préserver un graphe d’historique sémantiquement cohérent et utile, lequel représente une véritable valeur ajoutée.

Tous les autres cas de figure relèvent du `rebase` sous toutes ses formes : classique, tri-partite, interactif ou _cherry picking_.



### Merge

```text
git checkout feature
git merge master
```

+ non destructive / ne réécrit pas l'historique

-- creation de commit de merge dans la branche-feature \(pollution de l'historique si plusieurs commit de merge\)

commit de merge donne du context, vous pouvez mieux voir à quel moment des changements apportés au dépôt upstream ont été intégrés à la branche de fonctionnalité.

-Le rebase est une méthode courante pour intégrer les changements en amont dans votre dépôt local. L'intégration des changements en amont avec git merge génère un commit de merge superflu dès que vous voulez voir comment le projet a évolué.



### Rebase

```text
git checkout feature
git rebase master
```

-- reecrit l'histoirque \(\)

+ les commits de la branches sont tjrs a fin \(facilite le fast-forward\)

+ historique linéaire, plus propre, plus lisible

+ pas de commit supplementaire \(commit de merge\)

-- respecter des regles strictes a cause de la reecriture de l'historique





#### Rebaser ou Fusionner <a id="_rebaser_ou_fusionner"></a>

De manière générale, la manière de profiter au mieux des deux mondes consiste à rebaser des modifications locales que vous avez effectuées mais qui n’ont pas encore été partagées avant de les pousser de manière à obtenir un historique propre mais sans jamais rebaser quoi que ce soit que vous ayez déjà poussé quelque part.



## Source

{% embed url="https://www.atlassian.com/fr/git/tutorials/merging-vs-rebasing" %}

{% embed url="https://delicious-insights.com/fr/articles/bien-utiliser-git-merge-et-rebase/" %}



