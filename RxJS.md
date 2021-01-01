# RxJS : Découverte par un noob

## Définition

RxJS est l’implémentation en JavaScript de ReactiveX (http://reactivex.io). ReactiveX est une API pour la programmation asynchrone grâce aux flux observable. En un mot, RxJS est une bibliothèque d'outil permettant de gérer facilement les évènements asynchrones.

## Situation d'utilisation

Il y a de nombreuses sources de données, pour ne pas dire que tous est une source de données. Si l'on veux, par exemple, les afficher, nous faisons X méthodes qui récupère et afficher chaque sources. Mais si maintenant nous voulons compter le nombre de résultat retourné pour chaque sources, il faudra refaire X méthodes qui vont récupérer puis afficher le compte. Pas optimal comme situation.

## Penser de façon : programmation reactive

La source ne devient plus QUE responsable de la récupération des données, et prévenir qu'il y a des nouvelles données. Si l'on veux afficher les données, une méthode prendra les données à disposition et les affichera quelque soit la source.

 Il faut se poser2 questions :

- Comment est-ce qu'on met à disposition une source de données avec RxJS?
- Comment est-ce qu'on réagit à celle-ci ?

La source de données est un **Observable** (voir design Pattern Observer).

Grace a l’observer

### Exemple :

`import { fromEvent } from 'rxjs'; `

`fromEvent(document, 'click')` fromEvents crée un Observable a partir d'un événement de clic

`.subscribe(() => console.log('Clicked!'));` L'Observer est console.log





Cela 

## Un point sur les design pattern utilisé

ReactiveX combine le modèle Observer avec le modèle Iterator et la programmation fonctionnelle avec des collections pour répondre au besoin d'une manière idéale de gérer les séquences d'événements.

Basé sur les pattern :

- Observer pattern
- Iterator pattern
- and functional programming





## Concept de base

- Observable: représente l'idée d'une collection invocable de valeurs ou d'événements futurs.
- Observer: est une collection de callbacks qui sait écouter les valeurs délivrées par l'Observable.
- Abonnement: représente l'exécution d'un Observable, est principalement utile pour annuler l'exécution.
- Opérateurs: ce sont des fonctions pures qui permettent un style de programmation fonctionnel de traiter des collections avec des opérations telles que mapper, filtrer, concaténer, réduire, etc.
- Sujet: équivaut à un EventEmitter et est le seul moyen de multidiffuser une valeur ou un événement vers plusieurs observateurs.
- Schedulers: sont des répartiteurs centralisés pour contrôler la concurrence, nous permettant de coordonner lorsque le calcul se produit, par exemple. setTimeout ou requestAnimationFrame ou autres.

**opérateurs**

**Observable** 

 **Subject** est à la fois un observable ET un observateur. On peut donc **subscribe** dessus, mais également lui envoyer des valeur

## Sources

- https://www.julienpradet.fr/tutoriels/introduction-a-rxjs
- https://makina-corpus.com/blog/metier/2017/premiers-pas-avec-rxjs-dans-angular
- http://reactivex.io
- https://rxjs.dev/guide/overview
- 



