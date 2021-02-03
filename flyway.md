# Flyway

## Qu'est ce que c'est ?



Toutes modif a la BDD est une 'migration' pour flyway

Pour garder une trace des migrations qui ont déjà été appliquées, quand et par qui, Flyway ajoute une table d'historique de schéma à votre schéma.

### Migration versionné :

* les plus courante 
* a une description et un checksum
* on une version fixe et unique
* appliqué 1 seul fois et dans l'ordre
* peut etre annulé avec une migration 'undo'

Création / modification / suppression de tables / index / clés étrangères / enums / UDT /… Mises à jour des données de référence Corrections des données utilisateur

### Migration répétable

* description
* checksum
* mais pas de version
* se reexecute si la checksum change
* elles sont executé a la fin de tous les script

Les migrations répétables ont une description et une somme de contrôle, mais pas de version. Au lieu d'être exécutés une seule fois, ils sont \(ré\) appliqués à chaque fois que leur somme de contrôle change.

Ceci est très utile pour gérer des objets de base de données dont la définition peut ensuite être simplement maintenue dans un seul fichier en contrôle de version. Ils sont généralement utilisés pour

\(Re-\) création de vues / procédures / fonctions / packages /… Réinsertion de données de référence en masse

Il est de votre responsabilité de vous assurer que la même migration répétable peut être appliquée plusieurs fois. Cela implique généralement l'utilisation de clauses CREATE OR REPLACE dans vos instructions DDL.

### Undo Migration

c'est le contraire des migration versionné

...



### Migrations basées sur SQL

Les migrations sont le plus souvent écrites en SQL. Cela facilite la mise en route et l'exploitation des scripts, outils et compétences existants. Il vous donne accès à l'ensemble des fonctionnalités de votre base de données et élimine le besoin de comprendre toute couche de traduction intermédiaire.

Les migrations basées sur SQL sont généralement utilisées pour

* Modifications DDL \(instructions CREATE / ALTER / DROP pour TABLES, VIEWS, TRIGGERS, SEQUENCES,…\)
* Modifications simples des données de référence \(CRUD dans les tableaux de données de référence\)
* Modifications simples des données en masse \(CRUD dans les tableaux de données réguliers\)



Nommage des fichiers



## Callbacks <a id="callbacks"></a>

While migrations are sufficient for most needs, there are certain situations that require you to **execute the same action over and over again**. This could be recompiling procedures, updating materialized views and many other types of housekeeping.

For this reason, Flyway offers you the possibility to **hook into its lifecycle** by using Callbacks.

These are the events Flyway supports:





