← Étape précédente : [04. MCP](04-mcp.md) | [Sommaire](../README.md) | Étape suivante : [06. Plugins](06-plugins.md) →

# Étape 05. Subagents, les spécialistes

## Objectif

Créer un subagent : un assistant dédié à une tâche, avec son propre contexte et ses propres outils.

## En clair

Un **subagent** est un assistant spécialisé que Claude peut appeler. Il a sa propre fenêtre de contexte (donc il n'encombre pas la conversation principale), son propre prompt système, et on peut lui restreindre les outils auxquels il a droit.

Deux bénéfices concrets : la spécialisation (un agent « relecteur de code » fait mieux qu'une consigne noyée dans un long échange) et l'isolation (le travail lourd se fait à côté, le fil principal reste lisible). Claude délègue à un subagent en se basant sur sa **description**.

## En pratique

Un subagent est un fichier dans `.claude/agents/` (pour le projet) ou `~/.claude/agents/` (pour vous, sur tous vos projets).

Créons un relecteur de code. Fichier `.claude/agents/relecteur-code.md` :

```markdown
---
name: relecteur-code
description: Relit le code récemment modifié et signale bugs, risques et incohérences. À utiliser après avoir écrit ou changé du code.
tools: Read, Grep, Glob
---

Tu es un relecteur de code rigoureux et bienveillant.

- Concentre-toi sur les fichiers récemment modifiés.
- Signale en priorité les bugs réels et les risques de sécurité.
- Pour chaque point, donne le fichier, la ligne et une correction concrète.
- Ne réécris pas tout : vise les problèmes qui comptent vraiment.
```

Notez le champ `tools` : ici, le relecteur ne peut que lire et chercher, pas modifier. C'est plus sûr. Un exemple prêt à copier est dans [`exemple-starter/`](../exemple-starter/).

Ensuite, demandez à Claude de relire vos changements : il appellera le subagent quand la description correspond.

## Piège fréquent

Comme pour les skills, tout se joue dans la `description`. Si elle est floue, Claude ne saura pas quand déléguer. Et résistez à la tentation de créer dix agents dès le premier jour : un ou deux agents utiles valent mieux qu'une collection que vous n'utilisez pas.

## Étape suivante

La page officielle détaille le format complet, les champs et la gestion des permissions : [code.claude.com/docs/en/sub-agents](https://code.claude.com/docs/en/sub-agents).

Vous savez créer chaque brique à la main. Voyons comment installer des ensembles tout prêts.

→ [06. Plugins](06-plugins.md)
