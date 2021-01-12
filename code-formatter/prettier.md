# Prettier

Un des outils de formatage de code les plus téléchargé et multi langage est Prettier.

{% embed url="https://prettier.io/" %}

### Prettier ?

Prettier est un outil de formatage de code prenant en charge beaucoup de langages : JavaScript / JSX / **Angular** / Vue / Flow / **TypeScript** / **CSS**, Less, and SCSS / **HTML** / **JSON** / GraphQL / **Markdown**, including GFM and MDX / YAML. Les développeurs de Prettier ont donc cherché des consensus sur les règles de formatage pour créer une cohérence dans le formatage.

### Comment voir si vous utilisez bien Prettier ?

Dans VScode, lorsque vous ouvré un fichier compatible avec Prettier. En bas à droite de la fenêtre, vous devez avoir un texte : "Prettier : ✔" Ce qui signifie que Prettier est le formateur pour se type de fichier.

### Comment tester si vous utilisez bien Prettier ?

* A la racine du projet, dans le fichier **.prettierrc**, modifier la valeur de **tabWidth** par **4**, par exemple.
* Sauvegarder le fichier **.prettierrc**
* Puis ouvrer un fichier typeScript \(.ts\)
* Forcer le formatage avec : Alt + Ctrl + F
* Si l’indentation change, alors Prettier est bien l’outil de formatage pour les fichier typeScript \(.ts\)
* Refaire la même action pour les différents types de fichier \(.html ; .css ; …..\)
* Restauré votre fichier .prettierrc et vos autres fichiers après le test.

