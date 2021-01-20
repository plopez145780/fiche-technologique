---
description: Liste tout ce qui a été fait dans git
---

# Reflog

`git reflog` ou `git reflog show` affiche l'historique des références. C'est pourquoi, la commande se nomme 'reflog' pour **ref**erence **log**s.

Les références sont les noms simple permettant de pointer vers la valeur SHA-1 d'un commit. Les branches, les branches de suivie distant, et les tags sont toutes des références à des commits.

Exemple :

* La branche "test" est un raccourci pour "refs/heads/test".
* Le tag "v2.6.18" est un raccourci pour "refs/tags/v2.6.18".
* "origin/master" est un raccourci pour "refs/remotes/origin/master".

A chaque ajout, suppression, modification d'un commit la référence de la branche change, pour pointé sur le nouveau commit. L'historique des réferences 'reflog' stocke tous ces changements. D'une certaine manière, cela correspond à enregistrer toutes les actions réalisé.

## Source

### Reflog

{% embed url="https://git-scm.com/docs/git-reflog" %}

{% embed url="https://www.atlassian.com/fr/git/tutorials/rewriting-history/git-reflog" %}

### Reférences

{% embed url="https://git-scm.com/book/en/v2/Git-Internals-Git-References" %}

{% embed url="https://alexgirard.com/git-book/interne/references-git/" %}



