[Sommaire](README.md)

# Aide-mémoire (cheatsheet)

L'essentiel à portée de main : les commandes, raccourcis et gestes du quotidien. Vérifié sur la documentation officielle le **2026-06-22**. Les raccourcis peuvent varier selon le terminal et la plateforme ; la référence qui fait autorité reste [code.claude.com/docs](https://code.claude.com/docs/en/overview).

> Claude Code évolue vite : certaines commandes apparaissent ou disparaissent selon la version et le plan. Tapez `/` dans une session pour voir les commandes réellement disponibles chez vous, et `claude --version` pour connaître votre version.

## Lancer et reprendre

| Commande | Rôle |
|---|---|
| `claude` | Ouvrir une session interactive |
| `claude "votre demande"` | Session avec un prompt initial |
| `claude -c` | Reprendre la dernière conversation du dossier (`--continue`) |
| `claude -r "<session>" "demande"` | Reprendre une conversation par ID ou nom (`--resume`) |
| `claude -p "demande"` | Mode impression (headless), une réponse puis sortie (`--print`) |
| `claude update` | Mettre à jour Claude Code |
| `claude --version` | Afficher la version installée |

## Commandes essentielles en session

| Commande | Rôle |
|---|---|
| `/help` | Aide et liste des commandes |
| `/clear` | Nouvelle conversation, contexte vide (l'ancienne reste dans `/resume`) |
| `/compact` | Résumer la conversation pour libérer du contexte |
| `/context` | Visualiser l'usage du contexte |
| `/init` | Générer un CLAUDE.md de départ |
| `/memory` | Éditer les CLAUDE.md, gérer la mémoire |
| `/model` | Changer de modèle |
| `/config` | Réglages (thème, modèle, mode éditeur...) |
| `/status` | Version, modèle, compte, connectivité |
| `/usage` | Coût et limites (alias `/cost`) |
| `/resume` | Reprendre une conversation précédente |
| `/rewind` | Revenir code et conversation à un point antérieur (alias `/undo`) |

## Outils et extensions

| Commande | Rôle |
|---|---|
| `/agents` | Gérer les subagents |
| `/mcp` | Gérer les connexions MCP, statut et reconnexion |
| `/plugin` | Gérer les plugins (lister, installer, activer) |
| `/skills` | Lister les skills disponibles |
| `/hooks` | Voir les hooks configurés |
| `/permissions` | Régler autoriser, demander, refuser |
| `/doctor` | Diagnostiquer l'installation (taper `f` pour laisser Claude corriger) |

## Relire et vérifier

| Commande | Rôle |
|---|---|
| `/diff` | Visionneuse des changements non committés |
| `/review [PR]` | Revue d'une pull request en local |
| `/code-review` | Revue du diff (bugs et nettoyages), option `--fix` pour appliquer |
| `/security-review` | Analyse les changements pour des failles (injection, auth, fuite de données) |

## Raccourcis clavier

| Touche | Effet |
|---|---|
| `Échap` | Interrompre Claude en cours de réponse, sans perdre le travail fait |
| `Échap` `Échap` | Sur un champ vide, ouvrir le menu rewind |
| `Ctrl+C` | Interrompre ou effacer la saisie ; deuxième appui, quitter |
| `Ctrl+D` | Quitter la session |
| `Shift+Tab` | Faire défiler les modes de permission (default, acceptEdits, plan...) |
| `Ctrl+L` | Redessiner l'écran |
| `Ctrl+O` | Basculer la vue détaillée des outils (transcript) |
| `Ctrl+R` | Recherche inverse dans l'historique |
| `↑` / `↓` | Naviguer dans l'historique des commandes |

## Gestes de saisie

| Geste | Effet |
|---|---|
| `/` en début | Lancer une commande ou un skill |
| `!` en début | Mode shell : lance une commande et ajoute sa sortie au contexte |
| `@` | Mentionner un fichier (avec autocomplétion) |
| `#` en début | Ajouter une note en mémoire (selon la version ; sinon demandez « ajoute ceci au CLAUDE.md » ou `/memory`) |
| `\` puis Entrée | Saut de ligne, saisie multiligne (tous terminaux) |

> Dans VS Code, Cursor ou Zed, lancez `/terminal-setup` pour activer `Shift+Entrée` en multiligne.

## Mode headless en bref

| Option | Effet |
|---|---|
| `claude -p "..."` | Une réponse puis sortie (`--print`) |
| `--output-format json` | Sortie structurée (text, json, stream-json) |
| `--model <modèle>` | Choisir le modèle (alias court comme `sonnet` ou `opus`, ou nom complet) |
| `--add-dir <chemin>` | Ajouter un dossier de travail |
| `--permission-mode <mode>` | Forcer un mode (plan, acceptEdits, default...) |
| `--dangerously-skip-permissions` | Sauter les vérifications de permission. À éviter quand on débute, hors environnement isolé |

> Sur Windows, le pipe bash `cat fichier | claude -p "..."` s'écrit en PowerShell `Get-Content fichier | claude -p "..."`.

## Gérer les serveurs MCP

| Commande | Rôle |
|---|---|
| `claude mcp add <nom> -- <commande>` | Ajouter un serveur local (stdio). Le `--` sépare les options de Claude de la commande du serveur |
| `claude mcp add --transport http <nom> <url>` | Ajouter un serveur HTTP distant |
| `claude mcp list` | Lister les serveurs et leur état |
| `claude mcp get <nom>` | Voir les détails d'un serveur |
| `claude mcp remove <nom>` | Retirer un serveur |
| `--scope local\|project\|user` | Portée : ce projet seulement (défaut), `.mcp.json` partagé en équipe, ou tous vos projets |

> Sécurité : ne collez jamais un jeton en clair dans une commande MCP. Voir [securite-et-permissions.md](securite-et-permissions.md).

---

> À jour le 2026-06-22 : le mode vim passe désormais par `/config`, section Editor mode (l'ancienne commande `/vim` a été retirée), et `/pr-comments` a été retiré (demandez directement à Claude de regarder les commentaires d'une PR). Une commande a changé ou disparu ? Signalez-le via [CONTRIBUTING.md](CONTRIBUTING.md).
