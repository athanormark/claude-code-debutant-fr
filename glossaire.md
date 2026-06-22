[Sommaire](README.md)

# Glossaire

Les termes qui reviennent sans arrêt dès qu'on démarre avec Claude Code, définis simplement, avec un exemple. L'ordre suit le parcours, du plus simple au plus avancé.

> Termes vérifiés sur la documentation officielle le **2026-06-22**. Le vocabulaire de Claude Code évolue vite : en cas de doute, la référence qui fait autorité reste [code.claude.com/docs](https://code.claude.com/docs/en/overview).

## CLAUDE.md

Fichier Markdown lu automatiquement au démarrage de chaque session. C'est la mémoire durable du projet : stack, conventions, commandes utiles. Il existe à trois niveaux : à la racine du projet (versionné, partagé en équipe), dans `~/.claude/CLAUDE.md` (perso, tous projets), et `CLAUDE.local.md` (perso, ce projet, non committé).

Exemple : un CLAUDE.md qui note `Lancer : npm run dev` et `Tester : npm test` évite de réexpliquer le projet à chaque session.

> À pratiquer à l'étape [01. CLAUDE.md](parcours/01-claude-md.md).

## Skill

Un savoir-faire que vous packagez une fois et réutilisez ensuite. C'est un dossier contenant un fichier `SKILL.md` (un frontmatter avec `name` et `description`, puis des instructions). Il se déclenche tout seul quand la demande correspond à sa description, ou à la main via `/nom-du-skill`. Il vit dans `.claude/skills/<nom>/` (projet) ou `~/.claude/skills/<nom>/` (perso).

Exemple : un skill `message-de-commit` qui rédige un message propre à partir de `git diff`.

> À pratiquer à l'étape [02. Commandes et skills](parcours/02-commandes-et-skills.md).

## Slash command (commande)

Une instruction tapée en début de message, qui commence par `/`. Cela couvre les commandes intégrées (`/help`, `/clear`, `/compact`, `/model`, `/mcp`, `/agents`...) et les skills (un skill nommé `deploy` crée la commande `/deploy`). Une commande n'est reconnue qu'en début de message, le texte qui suit est passé en argument.

Exemple : taper `/clear` pour repartir sur un contexte vide. À noter : les anciennes commandes personnalisées ont fusionné dans les skills, ce sont désormais la même brique.

## Subagent

Un assistant spécialisé à qui Claude délègue une sous-tâche, avec son propre contexte vierge et ses propres outils. Il est défini par un fichier Markdown à frontmatter (`name`, `description`, `tools` optionnel) dans `.claude/agents/` (projet) ou `~/.claude/agents/` (perso). Pratique pour isoler un travail sans encombrer la conversation principale.

Exemple : un subagent `relecteur-code` qui relit un diff et remonte les problèmes, pendant que Claude garde le fil de la tâche en cours.

> À pratiquer à l'étape [05. Subagents](parcours/05-subagents.md) et dans le [pack d'agents](agents/).

## Hook

Une commande lancée par Claude Code quand un événement se produit (`PreToolUse`, `PostToolUse`, `SessionStart`, `Stop`...). Elle se déclare dans `settings.json`, pas dans un fichier séparé. Sert à formater le code après édition, injecter du contexte, ou bloquer une action. Un hook s'exécute sur votre machine avec vos droits.

Exemple : un hook `PostToolUse` sur `Edit|Write` qui lance le formateur après chaque modification.

> À pratiquer à l'étape [03. Hooks](parcours/03-hooks.md).

## MCP (Model Context Protocol)

Un standard ouvert qui connecte Claude à des outils et des sources externes (base de données, service web, navigateur). Chaque connexion est un serveur MCP. Sans MCP, Claude travaille sur vos fichiers ; avec MCP, il peut interroger un service extérieur. Documenté sur [modelcontextprotocol.io](https://modelcontextprotocol.io).

Exemple : un serveur MCP qui donne la documentation à jour d'une librairie pour éviter les hallucinations d'API.

> À pratiquer à l'étape [04. MCP](parcours/04-mcp.md).

## Plugin

Un paquet prêt à installer qui regroupe d'un coup des skills, subagents, hooks, commandes et serveurs MCP. Il s'installe et se met à jour en bloc, plutôt que fichier par fichier. Se gère avec `/plugin`.

Exemple : installer un plugin de revue de code donne en une fois ses commandes et ses agents.

> À pratiquer à l'étape [06. Plugins](parcours/06-plugins.md).

## Marketplace

Un catalogue depuis lequel on découvre et installe des plugins. Officiel et curé par Anthropic (`anthropics/claude-plugins-official`), communautaire relu par Anthropic (`anthropics/claude-plugins-community`), ou indépendant. On ajoute un marketplace, puis on installe ce qu'on veut.

Exemple : ajouter le marketplace officiel, puis installer un plugin depuis sa liste.

> Voir l'[annuaire par domaine](annuaire-par-domaine.md) et [ressources.md](ressources.md).

## Fenêtre de contexte (context window)

La quantité de texte que le modèle garde en tête en une fois : votre conversation, les fichiers lus, les consignes. Elle est limitée. Quand elle se remplit, l'attention se dilue et le coût monte. On la nettoie avec `/clear` (nouveau sujet) ou on la résume avec `/compact` ; `/context` montre où part la place.

Exemple : après une longue session, `/compact` résume la conversation pour libérer de la place sans tout perdre.

## Mode headless (impression, `-p`)

L'exécution de Claude Code sans session interactive : une commande qui rend une réponse puis se termine. On la lance avec `claude -p "votre demande"` (ou `--print`). On peut lui passer du contenu en entrée. Sert aux scripts, à l'intégration continue, à l'automatisation.

Exemple : `claude -p "résume ce log"` dans un script. Sur Windows en PowerShell, l'équivalent d'un pipe est `Get-Content erreurs.txt | claude -p "explique l'erreur"`.

## Permissions et sandbox

Claude Code demande votre accord avant une action sensible (lancer une commande, écrire un fichier). Vous gérez les règles autoriser, demander ou refuser via `/permissions`. Les modes de permission se font défiler avec `Shift+Tab`. L'option `--dangerously-skip-permissions` saute les vérifications : à éviter quand on débute.

Exemple : refuser par défaut les commandes destructrices, n'autoriser que la lecture et les commandes git sûres.

> Voir [securite-et-permissions.md](securite-et-permissions.md) et [bonnes-pratiques.md](bonnes-pratiques.md).

## Prompt caching (mise en cache du prompt)

Un mécanisme qui réutilise les parties stables de votre conversation déjà envoyées au modèle, pour réduire le coût et la latence des messages suivants. Vous n'avez en général rien à configurer. Utile à connaître pour comprendre pourquoi continuer une longue conversation coûte moins cher que tout recommencer.

Exemple : reprendre une session avec `claude -c` profite du cache, alors que repartir de zéro le perd.

---

Un terme vous manque ? Proposez-le via [CONTRIBUTING.md](CONTRIBUTING.md).
