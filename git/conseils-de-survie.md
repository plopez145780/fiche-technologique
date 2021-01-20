---
description: "\U0001F988Conseils de survie en environnement git hostile \U0001F405"
---

# Conseils de survie

## Conseils

### [J'ai fait un truc horrible, par pitié dites-moi que git peut voyager dans le temps !?!](https://ohshitgit.com/fr#magic-time-machine)

```text
git reflog
# liste tout ce que vous avez fait dans git,
# quelle que soit la branche !
# chaque entrée correspond à un index HEAD@{index}
# trouvez celui juste avant d'avoir tout cassé
git reset HEAD@{index}
# git est magique
```

Ça sert pour récupérer une suppression accidentelle, ou annuler des tentatives qui ont cassé le dépôt, ou s'en sortir après une mauvaise fusion, ou simplement revenir en arrière à un point où les choses fonctionnaient correctement. J'utilise BEAUCOUP `reflog`. Chapeau trèèèès bas aux nombreuuuuuuses personnes qui m'ont suggéré cette technique !

### [Je viens de commiter et il manque une toute petite modification !](https://ohshitgit.com/fr#modifier-le-dernier-commit)

```text
# faire votre correction
git add . # ou ajouter les fichiers un à un
git commit --amend --no-edit
# votre dernier commit contient désormais votre modification !
# ATTENTION : ne jamais amend-er les commits publics
```

Cela m'arrive généralement quand je commite puis lance des tests/lints... et PDM, j'ai oublié un espace après une virgule. Vous pouvez aussi faire le changement via un nouveau commit puis faire `rebase -i` afin de fusionner les deux commits, mais c'est minimum un million de fois plus rapide.

_Avertissement : Ne jamais faire un `amend` sur des commits déjà poussés vers une branche publique/partagée ! Uniquement ceux qui n'existent que dans votre copie locale ou vous irez au-devant de gros ennuis..._

### [Je veux corriger le message de mon dernier commit !](https://ohshitgit.com/fr#corriger-dernier-message-commit)

```text
git commit --amend
# suivre les instructions pour modifier le message de commit
```

Encore ces règles de formatage des messages de commit.

### [J'ai commité sur le master alors que ça aurait dû aller sur une nouvelle branche !](https://ohshitgit.com/fr#erreur-commit-master)

```text
# créer une nouvelle branche à partir du master actuel
git branch un-nom-de-nouvelle-branche
# supprimer le dernier commit du master
git reset HEAD~ --hard
git checkout un-nom-de-nouvelle-branche
# votre commit est désormais dans cette branche :)
```

Note : cela ne fonctionne pas si vous avez déjà poussé le commit vers une branche publique/partagée, et si vous avez essayé d'autres trucs avant. Vous devrez sans doute faire un `git reset HEAD@{number-of-commits-back}` au lieu de `HEAD~`. Bonjour tristesse. Et aussi, beaucoup beaucoup beaucoup de personnes ont proposé une méthode géniale pour que ce soit plus court que ce que j'avais réussi à faire. Merci à tous !

### [Je me suis trompé de branche pour mon commit !](https://ohshitgit.com/fr#commit-dans-mauvaise-branche)

```text
# annuler le dernier commit, mais conserver les modifications
git reset HEAD~ --soft
git stash
# passer sur la bonne branche
git checkout nom-de-la-branche-correcte
git stash pop
git add . # ou ajouter les fichiers un à un
git commit -m "votre message ici";
# maintenant vos modifications sont sur la bonne branche
```

Pas mal de gens ont conseillé d'utiliser `cherry-pick` dans ce cas-là, donc à vous de faire votre choix et d'utiliser ce qui vous semble le plus logique !

```text
# passer sur la bonne branche
git checkout nom-de-la-branche-correcte
# y récupérer le dernier commit du master
git cherry-pick master
# supprimer le dernier commit du master
git checkout master
git reset HEAD~ --hard
```

### [Je fais un diff mais rien ne se passe ?!](https://ohshitgit.com/fr#rendez-moi-mon-diff)

Quand vous avez modifié des fichiers, mais que `diff` ne renvoie rien, c'est sans doute que vous avez déjà "ajouté" ces fichiers à l'Index \(stage area\) et qu'il faut utiliser une option spéciale.

```text
git diff --staged
```

Classé dans ¯\\_\(ツ\)\_/¯ \(oui, je sais, c'est une fonctionnalité et pas un bug, mais c'est époustouflifiant, voire déconcertifiant la première fois où ça vous arrive !\)

### [Je veux annuler un truc genre 5 commits en arrière !](https://ohshitgit.com/fr#annuler-un-commit)

```text
# trouver le commit que vous devez annuler
git log
# se déplacer dans l'historique avec flèche haut / flèche bas
# une fois le commit trouvé, mémoriser son hash
git revert [hash mémorisé]
# git va créer un nouveau commit qui annule ce commit
# suivre les instructions pour éditer le message de commit
# ou contentez-vous d'enregistrer et valider
```

Il s'avère que vous n'avez pas besoin de chercher l'ancien fichier puis copier-coller son contenu dans le fichier actuel pour annuler ce qui a été modifié ! Si vous avez commité un bug, vous pouvez annuler votre livraison d'un seul coup avec `revert`.

Vous pouvez aussi annuler un seul fichier plutôt que le commit complet ! Mais bien entendu, ça ne serait pas vraiment du git si cela n'impliquait pas un jeu de commandes complètement différentes...

### [Je veux annuler la modification d'un fichier !](https://ohshitgit.com/fr#annuler-un-fichier)

```text
# trouver le hash d'un commit d'avant la modification
git log
# se déplacer dans l'historique avec flèche haut / flèche bas
# une fois le commit trouvé, mémoriser son hash
git checkout [hash mémorisé] -- path/to/file
# l'ancienne version du fichier est désormais dans l'index
git commit -m "Super, pas de copier/coller pour annuler"
```

Quand j'ai enfin réussi à capter le truc, c'était ENORME. ENORME ! ENAUUUUURME... Non mais sérieux ! C'est quoi ce putain de monde où on doit utiliser un `checkout --` pour annuler les modifications d'un fichier ? :shakes-fist-at-linus-torvalds:

### [Je laisse tomber.](https://ohshitgit.com/fr#je-repars-a-zero)

```text
cd ..
sudo rm -r depot-git-foireux
git clone https://some.github.url/depot-git-foireux.git
cd depot-git-foireux
```

Merci à Eric V. pour ce conseil. Par conséquent, en cas de réclamation à cause du `sudo`, voyez-ça directement avec lui...

Plus sérieusement, quand votre branche est devenue tellement foireuse que le plus simple c'est de revenir à l'état d'origine du dépôt distant, essayez cette méthode "homologuée git". Mais attention, c'est ferme et définitif : impossible de revenir en arrière !

```text
# obtenir la dernière version du serveur
git fetch origin
git checkout master
git reset --hard origin/master
# supprimer les fichiers et répertoires non archivés
git clean -d --force
# répéter checkout/reset/clean pour chaque branche problématique
```

## Source

{% embed url="https://ohshitgit.com/fr" %}



