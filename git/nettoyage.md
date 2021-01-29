# Nettoyage

## Supprimer ses branches locales mergées autre que master

git branch --merged \| grep -v -e master \| xargs git branch -d



{% embed url="http://www.piwai.info/2011/10/30/coup-de-balai-deblayer-les-branches-dun-repo-git/" %}



