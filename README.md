# Claude Code pour débutants (FR)

> Un parcours guidé, en français, pour démarrer avec Claude Code sans se noyer. On apprend les briques dans le bon ordre, et chaque étape renvoie vers le meilleur catalogue de la communauté pour aller plus loin.

[![Licence MIT](https://img.shields.io/badge/licence-MIT-blue.svg)](LICENSE)
[![Langue](https://img.shields.io/badge/langue-fran%C3%A7ais-blue.svg)](#)
[![Statut](https://img.shields.io/badge/statut-vivant-brightgreen.svg)](#feuille-de-route)
[![Contributions](https://img.shields.io/badge/PR-bienvenues-orange.svg)](CONTRIBUTING.md)

> **Projet indépendant.** Ce dépôt n'est ni affilié à Anthropic, ni officiel. Claude et Claude Code sont des marques d'Anthropic. La documentation qui fait autorité reste [code.claude.com/docs](https://code.claude.com/docs/en/overview). Ici, on vulgarise et on trace un chemin d'apprentissage.

## Contexte et rôle

Quand on découvre Claude Code, on tombe vite sur des dépôts qui listent 150 agents, 1000 skills et des dizaines de plugins. C'est précieux quand on sait ce qu'on cherche, et écrasant quand on débute. Résultat classique : on installe tout, on ne comprend rien, on désinstalle.

Le contenu francophone existe, mais il est dispersé dans des articles de blog. Côté dépôt GitHub, le vide est presque total pour qui veut apprendre dans l'ordre.

Dépôt rédigé et maintenu par Athanor Savouillan (Atelia Conseil), sous licence MIT.

---

## Fonctionnalités

Un seul parti pris : **on n'accumule pas, on ordonne.** Sept étapes courtes, de l'installation au premier plugin. Chaque étape explique une brique, la fait pratiquer sur un exemple minimal, signale le piège le plus fréquent, puis pointe vers le catalogue de référence pour creuser.

C'est volontairement opinionné et léger. Pour la profondeur et le volume, ce sont les grands catalogues qui font le travail, et on les cite à chaque étape.

### Le parcours

| Étape | Brique | Objectif |
|---|---|---|
| [00. Installation](parcours/00-installation.md) | Mettre en place | Installer, lancer, vérifier que tout fonctionne |
| [01. CLAUDE.md](parcours/01-claude-md.md) | La mémoire du projet | Donner du contexte durable à Claude |
| [02. Commandes et skills](parcours/02-commandes-et-skills.md) | Les raccourcis | Créer un `/raccourci` réutilisable |
| [03. Hooks](parcours/03-hooks.md) | Les automatismes | Déclencher une action sur un événement |
| [04. MCP](parcours/04-mcp.md) | Les connexions | Brancher un outil externe |
| [05. Subagents](parcours/05-subagents.md) | Les spécialistes | Déléguer à un assistant dédié |
| [06. Plugins](parcours/06-plugins.md) | Les paquets | Installer un ensemble prêt à l'emploi |
| [07. Aller plus loin](parcours/07-aller-plus-loin.md) | La suite | Les meilleurs catalogues de la communauté |

Compter une à deux heures pour tout le parcours, ou une étape par jour si on préfère prendre le temps.

### Un starter prêt à cloner

Le dossier [`exemple-starter/`](exemple-starter/) contient une configuration `.claude/` minimale et générique : un `CLAUDE.md` type, un skill d'exemple, un subagent d'exemple et un `settings.json` prudent. À copier dans un projet pour partir d'une base saine plutôt que d'une page blanche.

### Un pack d'agents à adopter

Le dossier [`agents/`](agents/) propose des subagents prêts à l'emploi : relecteur de code, explorateur, rédacteur de tests, débogueur, documentaliste, refactoreur. Copiez ceux qui vous servent dans votre `.claude/agents/` et adaptez-les. Mode d'emploi dans [agents/README.md](agents/README.md).

### Les meilleures skills

[`skills.md`](skills.md) présente une sélection de sources de skills publiques qui valent le détour, avec leur dépôt source vérifié, pour ne pas tout réinventer.

### Les bonnes pratiques

[`bonnes-pratiques.md`](bonnes-pratiques.md) rassemble les réflexes qui évitent les ennuis courants : donner du contexte, découper les tâches, gérer les permissions, relire avant de committer, protéger ses données.

### Annuaire des ressources

[`ressources.md`](ressources.md) rassemble les dépôts publics de référence (officiels et communautaires), avec leur lien, une description courte et la date de vérification. Tout ce qui est cité a été contrôlé en direct, sans chiffre inventé.

Pour choisir en fonction de votre besoin, [`annuaire-par-domaine.md`](annuaire-par-domaine.md) reprend ces ressources classées par domaine (méthodologie, qualité, MCP, cloud, documents, SEO), avec pour chacune le moment où elle sert et le piège à connaître.

### Glossaire

[`glossaire.md`](glossaire.md) définit simplement les termes qui reviennent partout : CLAUDE.md, skill, subagent, hook, MCP, plugin, fenêtre de contexte, mode headless. Un terme, une définition courte, un exemple.

### FAQ et erreurs fréquentes

[`faq-erreurs-frequentes.md`](faq-erreurs-frequentes.md) répond aux blocages les plus courants du démarrage (accès refusé, CLAUDE.md ignoré, contexte saturé, MCP qui ne se connecte pas) en mode symptôme, cause, solution.

### Aide-mémoire et repères

- [`cheatsheet.md`](cheatsheet.md) : les commandes, raccourcis et gestes du quotidien, vérifiés sur la doc officielle.
- [`choisir-skill-subagent-mcp-plugin.md`](choisir-skill-subagent-mcp-plugin.md) : quelle brique pour quel besoin, un arbre de décision.
- [`securite-et-permissions.md`](securite-et-permissions.md) : ne pas se faire mal (permissions, secrets, lire avant d'installer).
- [`pieges-du-debutant.md`](pieges-du-debutant.md) : les erreurs classiques et le bon réflexe.

### Feuille de route

Le détail de ce qui est livré, ce qui vient ensuite et ce qu'on refuse volontairement de faire est dans [ROADMAP.md](ROADMAP.md). Depuis la version 1 (parcours complet), le dépôt s'est enrichi de l'annuaire par domaine, du glossaire et de la FAQ des erreurs. Viennent ensuite l'aide-mémoire, l'arbre de décision des briques, la sécurité et les pièges du débutant.

---

## Stack

- Contenu : pages en Markdown, en français.
- Exemples de configuration : fichiers `CLAUDE.md`, skill (`SKILL.md`), subagents (Markdown) et `settings.json`, regroupés dans `exemple-starter/` et `agents/`.
- Outil visé : Claude Code.

---

## Résultats

- Un parcours de huit fichiers, de `parcours/00-installation.md` à `parcours/07-aller-plus-loin.md`.
- Six subagents prêts à l'emploi dans `agents/`.
- Un starter `.claude/` minimal dans `exemple-starter/`.
- Des références transverses : glossaire, FAQ des erreurs, aide-mémoire, arbre de décision, page sécurité et permissions, pièges du débutant, annuaire par domaine.

---

## Lancer le projet

Ce dépôt est un parcours de lecture, il n'y a rien à compiler.

```bash
git clone https://github.com/athanormark/claude-code-debutant-fr.git
cd claude-code-debutant-fr
```

Commencer par `parcours/00-installation.md`. Pour utiliser le starter, copier `CLAUDE.md` et le dossier `.claude/` de `exemple-starter/` à la racine de son projet ; pour un subagent :

```bash
mkdir -p ~/.claude/agents
cp agents/relecteur-code.md ~/.claude/agents/
```

### Prérequis

- Un abonnement **Claude payant** (voir [les offres](https://claude.com/pricing)) ou un accès **Console (API)**. Le plan gratuit de Claude.ai ne donne pas accès à Claude Code (vérifié le 2026-06-22 sur la doc officielle).
- macOS 13+, Windows 10 (1809+) ou une distribution Linux récente, avec 4 Go de RAM.
- À l'aise avec un terminal (ou l'application Desktop, plus douce pour débuter).

---

## Contribuer

Ce dépôt reste volontairement resserré (un parcours clair vaut mieux qu'un dump exhaustif). Les corrections de faits, de liens morts et de coquilles sont prioritaires. Voir [CONTRIBUTING.md](CONTRIBUTING.md) pour le périmètre et la marche à suivre.

## Support

Les questions générales passent par les issues, en mode entraide communautaire et sans garantie de délai. Voir [SUPPORT.md](SUPPORT.md). Pour un accompagnement encadré (installation, configuration sur mesure, formation d'équipe), c'est une prestation : [atelia-conseil.com](https://atelia-conseil.com).

## Licence

Code et contenu sous licence [MIT](LICENSE). Réutilisation libre, y compris commerciale, en conservant la mention de licence.

---

## Auteur

Athanor Savouillan · [Réalisations](https://atelia-conseil.com/realisations/) · [Atelia Conseil](https://atelia-conseil.com) · [GitHub](https://github.com/athanormark)

Atelia Conseil : automatisation, structuration de données et agents IA souverains pour les TPE et PME.

---

## English summary

A beginner friendly, French first learning path for Claude Code. Instead of dumping hundreds of agents and skills, it walks through the building blocks in order (install, project memory, commands and skills, hooks, MCP, subagents, plugins) with a minimal example at each step, and links out to the best community catalogs to go further.

Independent project, not affiliated with Anthropic. The authoritative documentation is [code.claude.com/docs](https://code.claude.com/docs/en/overview). An English translation of the full path is on the roadmap. Contributions welcome, see [CONTRIBUTING.md](CONTRIBUTING.md).
