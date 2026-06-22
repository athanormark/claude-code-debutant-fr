← Étape précédente : [03. Hooks](03-hooks.md) | [Sommaire](../README.md) | Étape suivante : [05. Subagents](05-subagents.md) →

# Étape 04. MCP, les connexions

## Objectif

Comprendre ce qu'est un serveur MCP et en brancher un, pour donner à Claude l'accès à un outil ou une donnée externe.

## En clair

**MCP** veut dire Model Context Protocol. C'est un standard ouvert qui permet de connecter Claude à des outils et des sources de données : une base, un service web, votre gestionnaire de tickets, un navigateur. Sans MCP, Claude travaille sur vos fichiers. Avec MCP, il peut interroger un service extérieur.

Chaque connexion est un « serveur MCP ». Vous en ajoutez autant que de besoin, et vous gardez la main : un serveur ne fait que ce que ses outils permettent.

## En pratique

L'ajout se fait en ligne de commande. La forme générale :

```bash
claude mcp add <nom> -- <commande pour lancer le serveur>
```

Quand vous l'ajoutez au niveau du projet, Claude Code écrit la configuration dans un fichier `.mcp.json` à la racine, que vous pouvez versionner pour l'équipe.

Pour voir les serveurs configurés et leur état de connexion :

```bash
claude mcp list
```

Commencez par un serveur dont vous comprenez l'usage, vérifiez qu'il apparaît bien connecté, puis demandez à Claude une tâche qui s'appuie dessus.

## Piège fréquent

Un serveur MCP tourne avec vos accès et peut envoyer des données à un service tiers. Avant d'en brancher un, posez-vous deux questions : d'où vient ce serveur, et à quoi accède-t-il ? Pour des données sensibles, privilégiez des serveurs locaux ou que vous maîtrisez : c'est le bon réflexe dès le départ.

## Étape suivante

Le standard est documenté sur [modelcontextprotocol.io](https://modelcontextprotocol.io), et l'intégration côté Claude Code sur la doc officielle : [code.claude.com/docs](https://code.claude.com/docs/en/overview).

Vous savez connecter des outils. Voyons comment déléguer un travail entier à un assistant spécialisé.

→ [05. Subagents](05-subagents.md)
