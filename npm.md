# npm

## Prune

```text
npm prune [[<@scope>/]...] [--production] [--dry-run] [--json]
```

Cette commande supprime les packages "superflus". Si un nom de package est fourni, seuls les packages correspondant à l'un des noms fournis sont supprimés.

Les packages superflus sont ceux présents dans le dossier node\_modules qui ne sont répertoriés comme liste de dépendances d'aucun package.

[https://docs.npmjs.com/cli/v7/commands/npm-prune](https://docs.npmjs.com/cli/v7/commands/npm-prune)

## Outdated

```text
npm outdated [[<@scope>/]<pkg> ...]
```

Cette commande vérifiera le registre pour voir si des packages installés \(ou spécifiques\) sont actuellement obsolètes.

Par défaut, seules les dépendances directes du projet racine sont affichées. Utilisez --all pour rechercher également toutes les méta-dépendances obsolètes.

[https://docs.npmjs.com/cli/v7/commands/npm-outdated](https://docs.npmjs.com/cli/v7/commands/npm-outdated)

## Update

```text
npm update [-g] [<pkg>...]

aliases: up, upgrade
```

Cette commande mettra à jour tous les packages répertoriés avec la dernière version \(spécifiée par la balise config\), en respectant semver.

[https://docs.npmjs.com/cli/v7/commands/npm-update](https://docs.npmjs.com/cli/v7/commands/npm-update)

## 

