# Divers

## Supprimer ses branches locales mergées autre que master

git branch --merged \| grep -v -e master \| xargs git branch -d

## Supprimer ses branches locales mergées autre que master & develop

git branch --merged \| grep -v -e master -e develop \| xargs git branch -d

## Supprimer le dernier commit en local

git reset --soft HEAD~1

## Connaître le contenu d'un commit

git log  
git show --pretty= --name-only _idDuCommit_

## Annuler un git add

git reset &lt;file&gt;  
git reset

