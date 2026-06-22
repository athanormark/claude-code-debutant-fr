← Étape précédente : [01. CLAUDE.md](01-claude-md.md) | [Sommaire](../README.md) | Étape suivante : [03. Hooks](03-hooks.md) →

# Étape 02. Commandes et skills

## Objectif

Créer votre premier skill réutilisable, déclenché par un `/raccourci`.

## En clair

Un **skill** est un savoir-faire que vous packagez une fois et que Claude réutilise ensuite. Concrètement, c'est un dossier qui contient un fichier `SKILL.md` : un en-tête (le frontmatter) avec une description, puis des instructions en Markdown.

Deux façons de le déclencher :

- automatiquement, quand votre demande correspond à la description du skill,
- manuellement, en tapant `/nom-du-skill`.

Bon à savoir, car beaucoup de vieux tutoriels l'ignorent : les anciennes **commandes personnalisées ont été fusionnées dans les skills**. Un fichier `.claude/commands/deploy.md` et un skill `.claude/skills/deploy/SKILL.md` créent tous les deux la commande `/deploy`. Les anciens fichiers `commands/` continuent de fonctionner, mais un nouveau skill se crée désormais sous `skills/`.

## En pratique

Comme pour `CLAUDE.md`, un skill vit à deux endroits :

- `~/.claude/skills/<nom>/SKILL.md` pour un skill perso, disponible sur tous vos projets,
- `.claude/skills/<nom>/SKILL.md` pour un skill propre au projet, partagé avec l'équipe.

Créons un skill qui rédige un message de commit propre. Fichier `.claude/skills/message-de-commit/SKILL.md` :

```markdown
---
name: message-de-commit
description: Rédige un message de commit clair à partir des changements en cours. À utiliser avant de committer.
---

# Message de commit

1. Regarde les changements avec `git diff --staged`.
2. Résume l'intention en une ligne courte, à l'impératif.
3. Si besoin, ajoute deux ou trois puces pour le détail.
4. Propose le message, ne committe pas sans validation.
```

Relancez `claude` et tapez `/message-de-commit`. Le skill s'exécute.

Un exemple prêt à copier se trouve dans [`exemple-starter/`](../exemple-starter/).

## Piège fréquent

La `description` du frontmatter n'est pas décorative : c'est elle qui dit à Claude **quand** déclencher le skill tout seul. Une description vague (« aide au code ») ne se déclenche jamais au bon moment. Soyez précis sur le quand.

## Étape suivante

Les skills suivent un standard ouvert documenté sur [agentskills.io](https://agentskills.io), et la page officielle décrit le format en détail : [code.claude.com/docs/en/skills](https://code.claude.com/docs/en/skills).

Un skill agit quand vous l'appelez. Voyons comment déclencher une action toute seule, sur un événement.

→ [03. Hooks](03-hooks.md)
