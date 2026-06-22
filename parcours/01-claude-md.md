← Étape précédente : [00. Installation](00-installation.md) | [Sommaire](../README.md) | Étape suivante : [02. Commandes et skills](02-commandes-et-skills.md) →

# Étape 01. CLAUDE.md, la mémoire du projet

## Objectif

Écrire un premier fichier `CLAUDE.md` qui donne à Claude le contexte stable de votre projet, pour ne plus avoir à le répéter à chaque session.

## En clair

`CLAUDE.md` est un fichier que Claude Code lit automatiquement au démarrage, à chaque session. C'est la mémoire durable du projet : la stack, les conventions, les commandes utiles, ce qu'il faut faire et ne pas faire.

Il existe à trois niveaux :

- `CLAUDE.md` à la racine du projet : partagé avec l'équipe, versionné.
- `~/.claude/CLAUDE.md` : vos règles personnelles, valables sur tous vos projets.
- `CLAUDE.local.md` : vos notes perso pour ce projet, à ne pas committer.

## En pratique

Créez un fichier `CLAUDE.md` à la racine de votre projet. Un bon premier jet tient en quelques lignes :

```markdown
# Projet : (nom)

## Stack
- (langage, framework, base de données)

## Commandes
- Lancer : `npm run dev`
- Tester : `npm test`
- Build : `npm run build`

## Conventions
- (style de code, nommage, ce qui est interdit)

## À savoir
- (pièges connus, dossiers à ne pas toucher)
```

Lancez `claude`, demandez une petite tâche, et observez : Claude tient compte du fichier sans que vous ayez à le rappeler.

Quand le fichier grossit, gardez-le court et découpez. Vous pouvez importer un autre fichier avec la syntaxe `@chemin/vers/fichier.md`, ce qui garde le `CLAUDE.md` lisible.

## Piège fréquent

Deux excès se valent en mal. Le fichier vide, qui ne sert à rien. Et le fichier fleuve de 300 lignes, qui dilue les consignes importantes et alourdit chaque session. Visez l'essentiel : ce qu'un nouveau coéquipier aurait besoin de savoir le premier jour.

## Étape suivante

La page officielle sur la mémoire détaille les niveaux et les imports : [code.claude.com/docs](https://code.claude.com/docs/en/overview).

Votre projet a maintenant un contexte. Voyons comment vous fabriquer des raccourcis.

→ [02. Commandes et skills](02-commandes-et-skills.md)
