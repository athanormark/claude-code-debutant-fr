[Sommaire](README.md)

# Annuaire par domaine

Les ressources publiques de l'écosystème Claude Code, classées par usage, avec pour chacune le moment où elle sert et le piège à connaître. C'est la vue complète de [ressources.md](ressources.md), réorganisée par domaine pour choisir en fonction de votre besoin.

> **Méthode et fraîcheur.** Chaque dépôt a été vérifié le **2026-06-22**. Les nombres d'étoiles sont des ordres de grandeur à cette date : ils évoluent vite, ne les prenez pas au mot. Tout ce qui n'a pas pu être confirmé est écarté plutôt que cité au hasard. Un lien mort ou un dépôt abandonné ? Signalez-le (voir [CONTRIBUTING.md](CONTRIBUTING.md)).

## Comment lire cette page

- Commencez toujours par les **points d'entrée officiels**, ils font autorité.
- Une ressource notée **officielle Anthropic** est la plus sûre pour débuter.
- Avant d'installer quoi que ce soit de communautaire, lisez tout le dossier (pas seulement le README) et testez sur un projet jetable.

## Points d'entrée officiels

À consulter en premier. Détail dans [ressources.md](ressources.md) (section Officiel).

| Dépôt | Quand l'utiliser | Repère |
|---|---|---|
| [code.claude.com/docs](https://code.claude.com/docs/en/overview) | La documentation qui fait autorité, à garder sous la main | Source officielle |
| [anthropics/claude-code](https://github.com/anthropics/claude-code) | Suivre le changelog, signaler un bug | ~134 000 étoiles |
| [anthropics/claude-plugins-official](https://github.com/anthropics/claude-plugins-official) | Le marketplace de plugins curé par Anthropic | ~30 600 étoiles |

## Méthodologie et workflow de développement

Pour acquérir de bons réflexes : tests d'abord, débogage méthodique, planification, revue avant livraison. Le plus gros levier pour un débutant.

| Dépôt | Quand l'utiliser | Repère |
|---|---|---|
| [obra/superpowers](https://github.com/obra/superpowers) | Brainstorming, tests d'abord, débogage systématique, écriture de plans, vérification avant livraison | ~236 000 étoiles, MIT |
| [feature-dev](https://github.com/anthropics/claude-plugins-official) (plugin officiel) | Le workflow complet d'une fonctionnalité, du repérage à la relecture. Excellent premier plugin | marketplace officiel, ~30 600 étoiles |
| [commit-commands](https://github.com/anthropics/claude-plugins-official) (plugin officiel) | Les commandes `/commit`, `/commit-push-pr`, `/clean_gone` pour le quotidien git | marketplace officiel |

> Note débutant : `superpowers` est un plugin qui installe aussi des hooks de démarrage de session et une télémétrie de version (désactivable). Raison de plus pour lire le dossier avant de l'installer globalement dans `~/.claude/`.

## Qualité du code, revue et débogage

Relire, simplifier, déboguer. Tous issus du marketplace officiel, donc sûrs pour débuter. Le repère est celui du dépôt marketplace.

| Dépôt | Quand l'utiliser | Repère |
|---|---|---|
| [code-review](https://github.com/anthropics/claude-plugins-official) (plugin officiel) | Une revue de code multi-agents avant un commit important. Il explique pourquoi il signale chaque point | marketplace officiel |
| [code-simplifier](https://github.com/anthropics/claude-plugins-official) (plugin officiel) | Épurer du code sans changer son comportement. Relisez et relancez les tests après | marketplace officiel |
| [pr-review-toolkit](https://github.com/anthropics/claude-plugins-official) (plugin officiel) | Relire une pull request avec des agents dédiés (tests, types, erreurs silencieuses) | marketplace officiel |

## Agents et subagents spécialisés

De grandes collections de subagents prêts à l'emploi. On clone ou on installe, puis on adapte. Voir aussi le [pack d'agents](agents/) de ce dépôt, déjà en français.

| Dépôt | Quand l'utiliser | Repère |
|---|---|---|
| [wshobson/agents](https://github.com/wshobson/agents) | Une très grosse collection (agents, skills, commandes). À piocher quand on sait ce qu'on cherche | ~37 000 étoiles, MIT |
| [VoltAgent/awesome-claude-code-subagents](https://github.com/VoltAgent/awesome-claude-code-subagents) | Une centaine de subagents documentés (backend, frontend, tests, déploiement) | ~22 200 étoiles, MIT |

> Note débutant : ces collections sont souvent multi-outils (Codex, Cursor en plus de Claude Code). Lisez le frontmatter de chaque agent avant adoption, certains demandent un accès `Bash` large.

## MCP servers (connexions à des outils externes)

Le protocole MCP branche Claude Code sur des outils externes (docs, GitHub, bases de données). Voir aussi l'étape [04. MCP](parcours/04-mcp.md).

| Dépôt | Quand l'utiliser | Repère |
|---|---|---|
| [upstash/context7](https://github.com/upstash/context7) | Récupérer la doc à jour d'une librairie pour éviter les API hallucinées. Le MCP le plus utile pour débuter | ~58 000 étoiles, MIT |
| [github/github-mcp-server](https://github.com/github/github-mcp-server) | Gérer dépôts, issues et PR depuis Claude Code | ~30 900 étoiles, MIT |
| [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) | Le catalogue de référence des serveurs MCP (filesystem, fetch, git) | ~87 000 étoiles |
| [yamadashy/repomix](https://github.com/yamadashy/repomix) | Compresser un dépôt entier en un fichier pour l'analyser. Scan de secrets intégré | ~26 000 étoiles, MIT |

> Note débutant : `github-mcp-server` demande un token GitHub. Créez un token dédié au minimum de droits, ne collez jamais un token à portée large.

## Cloud, automatisation et IA

Plutôt intermédiaire, à regarder une fois à l'aise avec le CLI en local.

| Dépôt | Quand l'utiliser | Repère |
|---|---|---|
| [czlonkowski/n8n-mcp](https://github.com/czlonkowski/n8n-mcp) | Construire et valider des workflows n8n depuis Claude Code | ~22 000 étoiles, MIT |
| [czlonkowski/n8n-skills](https://github.com/czlonkowski/n8n-skills) | Les skills expertes pour écrire des workflows n8n (en duo avec le MCP) | ~5 500 étoiles, MIT |
| [huggingface/skills](https://github.com/huggingface/skills) | Datasets, entraînement, LoRA, Spaces. Seulement si vous faites du ML | ~10 700 étoiles, Apache-2.0 |

> Note débutant : le MCP n8n de `czlonkowski` est le plus utilisé, ne pas le confondre avec un module officiel n8n. Il demande une instance n8n et des identifiants : testez sur un projet jetable. Un MCP Cloudflare officiel existe aussi (`cloudflare/mcp-server-cloudflare`), niveau avancé ; son repère n'a pas pu être reconfirmé cette fois, vérifiez-le sur le dépôt avant de vous y fier.

## Documents et productivité

| Dépôt | Quand l'utiliser | Repère |
|---|---|---|
| [Skills documents officielles](https://github.com/anthropics/skills) (docx, xlsx, pptx, pdf) | Lire et produire des fichiers Word, Excel, PowerPoint, PDF | sous-ensemble de `anthropics/skills`, ~154 000 étoiles |
| [claude-md-management](https://github.com/anthropics/claude-plugins-community) (communautaire) | Écrire et améliorer le CLAUDE.md à partir des changements de code, de la structure du projet et du contexte de session | marketplace communautaire |

> Note débutant : certaines skills documents sont source-available et pas en open source. Vérifiez la licence de la skill avant un usage commercial. Et un CLAUDE.md reste un document de pilotage : relisez toujours une mise à jour automatique.

## Spécialisé, à la carte

Ressources de niche, pertinentes selon le métier. Secondaires pour un débutant généraliste.

| Dépôt | Quand l'utiliser | Repère |
|---|---|---|
| [AgriciDaniel/claude-seo](https://github.com/AgriciDaniel/claude-seo) | 25 sous-skills SEO (technique, contenu, schema, GEO, local). Seulement si vous faites du SEO | ~9 500 étoiles, MIT |
| [aaron-he-zhu/seo-geo-claude-skills](https://github.com/aaron-he-zhu/seo-geo-claude-skills) | Skills et commandes SEO/GEO, avec connecteurs vers des outils tiers | ~2 200 étoiles, Apache-2.0 |
| [frontend-design](https://github.com/anthropics/claude-plugins-official) (plugin officiel) | Le design d'interface UI/UX, depuis le marketplace officiel | marketplace officiel |

## Listes curées et catalogues

Pratiques pour découvrir, souvent multi-outils. Détail dans [ressources.md](ressources.md) (section Listes curées).

| Dépôt | Quand l'utiliser | Repère |
|---|---|---|
| [hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) | La liste de référence centrée Claude Code | ~47 000 étoiles, rythme ralenti |
| [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) | Très grande liste de skills, pour piocher des idées | ~65 500 étoiles |

## À connaître, mais avec prudence

Des ressources encore citées ailleurs, à utiliser en connaissance de cause.

- **[hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code)** : maintenance ralentie (dernier push fin avril 2026). Utile, mais certaines entrées peuvent dater.
- **[0xfurai/claude-code-subagents](https://github.com/0xfurai/claude-code-subagents)** : peu actif (dernier push octobre 2025). À garder comme antériorité, pas comme recommandation vivante.
- **[ThibautMelen/claude-insane-guide](https://github.com/ThibautMelen/claude-insane-guide)** : guide FR non maintenu depuis novembre 2025. Cité pour l'honnêteté du paysage francophone.

---

Une ressource solide manque ici ? Proposez-la avec son lien, une description d'une ligne et la date de vérification : [CONTRIBUTING.md](CONTRIBUTING.md).
