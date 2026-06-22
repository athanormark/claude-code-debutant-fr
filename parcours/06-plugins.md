← Étape précédente : [05. Subagents](05-subagents.md) | [Sommaire](../README.md) | Étape suivante : [07. Aller plus loin](07-aller-plus-loin.md) →

# Étape 06. Plugins, les paquets prêts à l'emploi

## Objectif

Installer un plugin, c'est-à-dire un ensemble cohérent de skills, commandes, subagents, hooks et serveurs MCP, en une seule fois.

## En clair

Un **plugin** regroupe plusieurs briques (skills, commandes, subagents, hooks, serveurs MCP) dans un paquet versionné, installable d'un coup. Plutôt que de recréer chaque morceau à la main, vous installez un plugin maintenu par quelqu'un d'autre.

Les plugins se trouvent dans des **marketplaces**. Il y en a un officiel d'Anthropic, un communautaire relu par Anthropic, et des marketplaces tiers.

## En pratique

Le marketplace officiel est disponible d'office. Pour parcourir ce qui existe, tapez `/plugin` puis ouvrez l'onglet Discover. Pour installer, la forme est `nom@marketplace` :

```text
/plugin install github@claude-plugins-official
```

Pour ajouter le marketplace communautaire, puis y installer un plugin :

```text
/plugin marketplace add anthropics/claude-plugins-community
```

Et pour un marketplace tiers, on ajoute d'abord son dépôt, puis on installe. Par exemple avec la collection de wshobson :

```text
/plugin marketplace add wshobson/agents
/plugin install python-development
```

Un catalogue web existe aussi : [claude.com/plugins](https://claude.com/plugins).

## Piège fréquent

Un plugin tiers apporte ses skills, mais aussi ses hooks et ses serveurs MCP, qui s'exécutent chez vous. Avant d'installer un marketplace inconnu, regardez qui le maintient et ce qu'il contient. Préférez d'abord le marketplace officiel et le communautaire, qui passent par une relecture.

## Étape suivante

La doc officielle décrit l'installation et la découverte des plugins : [code.claude.com/docs/en/discover-plugins](https://code.claude.com/docs/en/discover-plugins).

Vous maîtrisez les sept briques. Place à la suite : les meilleurs catalogues pour continuer.

→ [07. Aller plus loin](07-aller-plus-loin.md)
