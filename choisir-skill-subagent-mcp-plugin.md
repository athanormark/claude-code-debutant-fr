[Sommaire](README.md)

# Quelle brique pour quel besoin ?

Skill, commande, subagent, hook, MCP, plugin : au début, ces briques se ressemblent toutes. Le parcours les enseigne une par une (étapes 02 à 06). Cette page ne les réexplique pas, elle vous aide à **choisir** la bonne face à un besoin concret.

## Les six briques en une phrase

| Brique | En une phrase | Étape |
|---|---|---|
| Skill | Un savoir-faire que vous packagez et invoquez par `/raccourci` | [02](parcours/02-commandes-et-skills.md) |
| Commande (slash command) | La façon d'invoquer un skill ou une commande intégrée, en tapant `/` | [02](parcours/02-commandes-et-skills.md) |
| Subagent | Un assistant à qui déléguer une tâche, avec son contexte et ses outils à lui | [05](parcours/05-subagents.md) |
| Hook | Une action déclenchée automatiquement par un événement | [03](parcours/03-hooks.md) |
| MCP | Une connexion vers un outil ou une donnée externe | [04](parcours/04-mcp.md) |
| Plugin | Un paquet qui installe plusieurs briques d'un coup | [06](parcours/06-plugins.md) |

À noter : la commande et le skill ne sont pas deux briques concurrentes. Un skill nommé `deploy` crée la commande `/deploy` : la commande est la façon d'invoquer le skill à la main.

## L'arbre de décision

Posez-vous les questions dans cet ordre, la première à laquelle vous répondez oui donne la brique.

1. Mon besoin doit-il se déclencher **tout seul** quand un événement arrive (un fichier est modifié, une session démarre) ? Oui, c'est un **hook** ([03](parcours/03-hooks.md)).
2. Mon besoin demande-t-il d'**atteindre un outil ou une donnée externe** à mes fichiers (base de données, service web, doc d'une librairie) ? Oui, c'est un **MCP** ([04](parcours/04-mcp.md)).
3. Mon besoin est-il une **tâche lourde à isoler**, avec ses propres outils, sans encombrer la conversation en cours (relecture, exploration, tests) ? Oui, c'est un **subagent** ([05](parcours/05-subagents.md)).
4. Mon besoin est-il un **savoir-faire répétable que je veux rejouer** dans la conversation, à la demande ? Oui, c'est un **skill** ([02](parcours/02-commandes-et-skills.md)), invoqué par `/raccourci`.
5. Je veux **tout ça d'un coup, déjà prêt et maintenu par quelqu'un** ? C'est un **plugin** ([06](parcours/06-plugins.md)).

## Skill ou subagent ? (la confusion la plus fréquente)

> Si vous voulez juste rejouer une procédure dans la conversation en cours, c'est un **skill**. Si vous voulez déléguer un travail lourd à côté, avec ses propres outils et son propre contexte pour ne pas encombrer le fil, c'est un **subagent**.

Le subagent a un contexte vierge et des outils restreints (champ `tools`). Le skill s'exécute dans le fil courant. Détail aux étapes [02](parcours/02-commandes-et-skills.md) et [05](parcours/05-subagents.md).

## Hook ou skill ?

> Le **hook** est déclenché par la machine, sur un événement, sans que vous demandiez quoi que ce soit. Le **skill** est déclenché par vous, ou par votre demande.

## MCP, ou rien du tout ?

Vous n'avez pas besoin de MCP pour travailler sur vos propres fichiers : Claude les lit déjà. Le MCP sert uniquement à atteindre un service ou une donnée **externe**. Avant d'en brancher un, demandez-vous si le besoin est vraiment hors de vos fichiers. Détail à l'étape [04](parcours/04-mcp.md).

## Quand prendre un plugin plutôt que bricoler

Un plugin installe plusieurs briques d'un coup, maintenues par quelqu'un d'autre. Le réflexe sain quand on débute : apprendre la brique à la main d'abord (le parcours), puis adopter un plugin quand le besoin est récurrent et le mainteneur fiable. Lisez tout le dossier avant d'installer, voir [securite-et-permissions.md](securite-et-permissions.md).

## Tableau besoin vers bon outil

| Besoin concret | Brique | Pourquoi |
|---|---|---|
| Formater le code automatiquement après chaque édition | Hook | déclenché par l'événement, sans le demander |
| Relire mes derniers changements dans un contexte propre | Subagent | tâche isolée, outils restreints en lecture |
| Réutiliser ma procédure de message de commit | Skill | savoir-faire que j'invoque par `/message-de-commit` |
| Interroger ma base de données ou un service web | MCP | accès à un outil externe à mes fichiers |
| Récupérer la doc à jour d'une librairie | MCP | donnée externe (par exemple `context7`) |
| Bloquer une commande dangereuse avant qu'elle ne parte | Hook | garde-fou déclenché sur l'événement |
| Installer d'un coup un ensemble revue de code complet | Plugin | paquet de plusieurs briques tout prêt |
| Explorer un gros codebase sans polluer ma session | Subagent | travail lourd, contexte séparé |

Honnêtement, certains besoins se couvrent de plusieurs façons (relire le code peut être un subagent ou un skill). L'arbre donne le choix le plus naturel, pas une vérité unique.

## Le piège à éviter

Tout faire en plugin, ou tout faire en agent, alourdit l'outil pour rien. Choisissez la brique qui colle au besoin. Voir [pieges-du-debutant.md](pieges-du-debutant.md) et [bonnes-pratiques.md](bonnes-pratiques.md) (partez d'un besoin réel, une chose à la fois).

---

Une question sur le choix d'une brique ? Proposez un cas via [CONTRIBUTING.md](CONTRIBUTING.md). Pour un accompagnement encadré, c'est une prestation : [atelia-conseil.com](https://atelia-conseil.com).
