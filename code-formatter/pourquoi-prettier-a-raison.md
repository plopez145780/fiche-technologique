# Pourquoi Prettier à raison ?

### Prettier ?

Prettier est un formateur de code prenant en charge beaucoup de langages : JavaScript / JSX / **Angular** / Vue / Flow / **TypeScript** / **CSS**, Less, and SCSS / **HTML** / **JSON** / GraphQL / **Markdown**, including GFM and MDX / YAML Les développeurs de Prettier ont donc cherché des consensus sur les règles de formatage pour créer une cohérence dans le formatage.

### Interrogation sur le formatage de Prettier

Il y a maintenant un moment, sur RACING, il y a eu des interrogations sur le formatage et des demandes pour changer les règles de l’outil Prettier.

### Prettier : libérateur des débats sur le formatage

Selon Prettier, toutes les discussions sur le formatage de code sont de la perte de temps dans les équipes de développement. La principale raison d'adopter Prettier est d'arrêter tous les débats sur les styles de formatages. C’est aussi pourquoi il n’y a pas beaucoup d’option de configuration \(environ 22 options\), afin de ne pas retomber dans le travers des débats sur les options à choisir.

### Le but de Prettier

Libérez les développeurs de la fatigue mentale du formatage au quotidien. Mais aussi ne pas passer son énergie mentale à trouver comment mieux formater le code. Le formatage, c'est Prettier qui s’en occupe, pas la peine d'y penser.

#### Source :

[https://prettier.io/docs/en/index.html](https://urldefense.proofpoint.com/v2/url?u=https-3A__prettier.io_docs_en_index.html&d=DwMFAw&c=eIGjsITfXP_y-DLLX0uEHXJvU8nOHrUK8IrwNKOtkVU&r=RDzdffwgYdAVs_L_RxSQl0jJGBvT1Uk_2wjGObLpppM&m=USIPd80eCy9YzMaG2MiX8heMRz3MxDqRx2F9EuRW0_s&s=HDIPfn64vP-wZiZE38uhFjlccQcQhIa53drNkK0FUPI&e=)

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

