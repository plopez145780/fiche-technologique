# Merge VS Rebase

## Situation 

Faire un merge entre 2 branche qui ont evolué



### Merge

```text
git checkout feature
git merge master
```

+ non destructive / ne réécrit pas l'historique

-- creation de commit de merge dans la branche-feature \(pollution de l'historique si plusieurs commit de merge\)

commit de merge donne du context, vous pouvez mieux voir à quel moment des changements apportés au dépôt upstream ont été intégrés à la branche de fonctionnalité.

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



## Source

{% embed url="https://www.atlassian.com/fr/git/tutorials/merging-vs-rebasing" %}



