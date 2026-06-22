← Étape précédente : [02. Commandes et skills](02-commandes-et-skills.md) | [Sommaire](../README.md) | Étape suivante : [04. MCP](04-mcp.md) →

# Étape 03. Hooks, les automatismes

## Objectif

Comprendre ce qu'est un hook et en mettre un en place, pour déclencher une action automatiquement sur un événement.

## En clair

Un **hook** est une commande lancée par Claude Code quand un événement se produit. Quelques événements courants :

- `PreToolUse` : juste avant que Claude utilise un outil (par exemple lancer une commande shell).
- `PostToolUse` : juste après.
- `SessionStart` : au démarrage d'une session.
- `Stop` : quand Claude a fini de répondre.

À quoi ça sert ? Formater le code après une modification, injecter du contexte au démarrage, ou bloquer une commande dangereuse. Détail important : un hook `PreToolUse` qui se termine avec le code de sortie 2 **annule** l'action que Claude allait faire. C'est le mécanisme de garde-fou.

Les hooks ne sont pas des fichiers séparés : ils se déclarent dans `settings.json` (au niveau projet ou global).

## En pratique

Voici un hook simple et inoffensif pour démarrer : un rappel après chaque modification de fichier. Dans `.claude/settings.json` :

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          {
            "type": "command",
            "command": "echo 'Fichier modifié, pense à relancer les tests.'"
          }
        ]
      }
    ]
  }
}
```

Le `matcher` choisit les outils concernés (ici les éditions de fichiers). Relancez une session, demandez une petite modification, et le message s'affiche.

## Piège fréquent

On voit trop grand, trop vite : un hook qui lance un build complet à chaque caractère tapé rend l'outil pénible. Commencez petit et inoffensif. Et rappelez-vous qu'un hook s'exécute sur votre machine, avec vos droits : ne collez jamais un hook trouvé en ligne sans le lire.

## Étape suivante

Le schéma exact des hooks et la liste complète des événements sont sur la doc officielle : [code.claude.com/docs](https://code.claude.com/docs/en/overview). Vérifiez-y toujours la syntaxe à jour avant de copier un exemple.

Un hook réagit à un événement local. Voyons maintenant comment brancher Claude sur des outils extérieurs.

→ [04. MCP](04-mcp.md)
