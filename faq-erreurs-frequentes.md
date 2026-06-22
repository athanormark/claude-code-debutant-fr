[Sommaire](README.md)

# FAQ, erreurs et blocages fréquents

Ces situations arrivent à presque tout le monde au début. Pour chacune : le symptôme, la cause probable, et comment s'en sortir. Pour les soucis d'installation, la doc officielle reste la référence : [code.claude.com/docs](https://code.claude.com/docs/en/overview).

> Avant tout : `/doctor` diagnostique l'installation et la config, `/status` montre la version, le modèle, le compte et la connectivité. À lancer en premier face à un comportement étrange.

## Accès refusé : « Claude Code n'est pas disponible sur votre plan »

- **Symptôme** : impossible de lancer Claude Code, message d'accès refusé.
- **Cause** : le plan gratuit de Claude.ai ne donne pas accès à Claude Code. Il faut un abonnement Claude payant ou un accès Console (API) ; les offres à jour sont sur [claude.com/pricing](https://claude.com/pricing).
- **Solution** : vérifier son plan, ou passer par l'API Console. C'est une limite de compte, pas un bug. Détail vérifié le 2026-06-22 sur la doc officielle.

## Claude ne respecte pas le CLAUDE.md

- **Symptôme** : une consigne pourtant écrite dans CLAUDE.md n'est pas suivie.
- **Cause** : fichier trop long (300 lignes diluent les consignes), règle noyée ou ambiguë, mauvais niveau (perso au lieu de projet), ou fichier non rechargé (il est lu au démarrage de session).
- **Solution** : raccourcir et hiérarchiser, formuler des règles concrètes et impératives, vérifier le bon niveau (racine du projet contre `~/.claude/CLAUDE.md`), relancer une session pour qu'il soit relu, éditer avec `/memory`. Voir [01. CLAUDE.md](parcours/01-claude-md.md).

## La fenêtre de contexte est saturée

- **Symptôme** : réponses plus lentes, plus chères, qui perdent le fil ou oublient le début.
- **Cause** : une longue session qui accumule fichiers lus et échanges ; la fenêtre de contexte se remplit.
- **Solution** : `/clear` pour repartir à zéro entre deux sujets sans rapport (le projet et le CLAUDE.md restent), `/compact` pour résumer une session utile devenue longue, `/context` pour voir où part la place. Découper le travail en tâches plus petites. À savoir : `/clear` démarre une nouvelle conversation, l'ancienne reste accessible via `/resume`.

## Trop de demandes de permission, ou au contraire trop autorisé

- **Symptôme** : Claude redemande l'autorisation à chaque commande (pénible), ou bien on a tout autorisé et une commande risquée est passée.
- **Cause** : réglages par défaut dans un cas, contournement des garde-fous (par exemple `--dangerously-skip-permissions`) dans l'autre.
- **Solution** : configurer des règles ciblées via `/permissions` (autoriser la lecture et `git log`, demander pour le reste, refuser les commandes destructrices). Ne jamais désactiver globalement les permissions quand on débute. `Shift+Tab` change de mode. Voir [bonnes-pratiques.md](bonnes-pratiques.md), section « Ne pas tout autoriser ».

## Annuler une action ou revenir en arrière

- **Symptôme** : Claude a modifié un fichier de travers, on veut annuler.
- **Cause** : une modification appliquée qu'on regrette.
- **Solution** : `/rewind` (alias `/undo`) ramène le code et la conversation à un point précédent ; sur un champ vide, un double `Échap` ouvre le menu de rewind. Toujours travailler dans un dépôt git : `git diff` montre les changements, `git restore` permet de revenir. Committer souvent, par petits lots, pour avoir des points de retour. À savoir : `Échap` simple interrompt Claude sans perdre le travail déjà fait.

## Claude invente un fichier, une fonction ou une API

- **Symptôme** : Claude référence un fichier, une méthode ou une API qui n'existe pas.
- **Cause** : il complète à partir d'un savoir général parfois périmé, surtout sur des librairies récentes, sans avoir lu la source réelle.
- **Solution** : lui demander de lire le fichier ou la doc avant d'agir ; brancher un MCP de documentation à jour (par exemple `context7`) ; vérifier soi-même avant d'exécuter ; donner le chemin exact plutôt que de laisser deviner. Ne jamais committer du code sans le relire. Voir [04. MCP](parcours/04-mcp.md).

## Un commit part avec le mauvais auteur

- **Symptôme** : un commit apparaît avec un nom ou un email d'auteur incorrect.
- **Cause** : la configuration git locale n'est pas la bonne pour ce dépôt, ou une config globale prend le dessus.
- **Solution** : vérifier avec `git config user.name` et `git config user.email` ; corriger au niveau du dépôt (sans `--global`) ; pour réparer le dernier commit, `git commit --amend --reset-author`. Définir l'identité avant de committer. C'est un réglage git, pas un réglage Claude Code.

```bash
git config user.email "vous@exemple.fr"
git commit --amend --reset-author
```

## Un serveur MCP ne se connecte pas

- **Symptôme** : un serveur MCP ajouté n'apparaît pas connecté, ses outils sont absents.
- **Cause possible** : commande ou URL erronée, arguments stdio mal séparés, scope inattendu (local par défaut, donc ce projet seulement), serveur projet en attente d'approbation, ou identifiant manquant.
- **Solution** : `claude mcp list` pour l'état, `/mcp` en session pour le statut et la reconnexion, `claude mcp get <nom>` pour les détails. Pour un serveur stdio, bien séparer les arguments avec `--`. Approuver un serveur projet en attente. Vérifier le scope (`--scope user` pour tous les projets). Ne jamais coller un jeton en clair. Voir [04. MCP](parcours/04-mcp.md).

```bash
claude mcp list
claude mcp add <nom> -- npx -y <paquet-mcp>
```

## Un skill ne se déclenche jamais tout seul

- **Symptôme** : un skill existe mais ne s'active jamais automatiquement.
- **Cause** : sa `description` est vague (par exemple « aide au code »), donc Claude ne sait pas quand l'utiliser ; ou il est mal placé ; ou il faut le recharger.
- **Solution** : écrire une description précise sur le quand (« Rédige un message de commit à partir des changements en cours, à utiliser avant de committer ») ; vérifier l'emplacement (`.claude/skills/<nom>/SKILL.md`) ; le déclencher à la main via `/nom-du-skill` pour tester. Voir [02. Commandes et skills](parcours/02-commandes-et-skills.md).

---

Un blocage manque ici ? Signalez-le via [CONTRIBUTING.md](CONTRIBUTING.md), voir aussi [SUPPORT.md](SUPPORT.md).
