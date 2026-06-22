[Sommaire](README.md)

# Sécurité et permissions : ne pas se faire mal

Claude Code agit sur **votre** machine avec **vos** droits. La sécurité n'est pas un sujet avancé, c'est un réflexe de premier jour. Cette page approfondit ce que [bonnes-pratiques.md](bonnes-pratiques.md) résume, sans le répéter. Aucune de ces mesures ne garantit zéro risque : elles le réduisent.

## Comprendre les permissions

Claude demande votre accord avant une action sensible (lancer une commande, écrire un fichier) ; vous autorisez au cas par cas. Les règles vivent à trois niveaux : `settings.json` (projet, versionné, partagé), `settings.local.json` (perso, non versionné), et les réglages globaux dans `~/.claude`. Il existe trois verbes : autoriser, demander, refuser. La syntaxe exacte évolue : pour le schéma à jour, voir [code.claude.com/docs](https://code.claude.com/docs/en/overview).

## Ne pas tout autoriser

Cliquer « autoriser » partout, ou lancer un mode qui contourne les validations, c'est se priver du seul garde-fou qui protège d'une commande destructrice (une suppression, un `git push` non voulu, une exfiltration de données). Le réflexe : n'élargir une permission que quand vous comprenez pourquoi. `--dangerously-skip-permissions` saute les vérifications : à laisser de côté quand on débute.

## Protéger ses secrets

Ne mettez jamais une clé, un token ou un mot de passe dans un CLAUDE.md, un skill, un prompt d'agent ou un fichier versionné. Le contenu versionné part sur GitHub, et le contenu d'un CLAUDE.md entre dans le contexte du modèle. Préférez une variable d'environnement ou un fichier `.env` hors du dépôt.

```
# .gitignore
.env
.claude/settings.local.json
```

```
# .env (non versionné)
API_KEY=VOTRE_CLE_ICI
```

## Verrouiller l'accès aux fichiers sensibles

Même un agent en lecture seule (`Read`, `Grep`, `Glob`) peut lire un `.env` ou une clé. D'où l'intérêt d'un `permissions.deny` sur ces chemins, pour fermer la porte. Ce point est déjà posé pour les agents dans [agents/README.md](agents/README.md) ; il vaut pour toute votre configuration.

## Méfiance avec Bash et Write

Un agent, un skill ou un hook qui peut exécuter des commandes (`Bash`) ou écrire des fichiers (`Write`) peut modifier ou casser votre machine. Réflexes : préférer les outils minimaux nécessaires (champ `tools` restreint), tester d'abord sur un projet jetable, garder les permissions au cas par cas.

> Un agent avec `Bash` peut lancer `rm` ou `git push`. Avant de l'adopter, faites-le tourner sur un projet jetable et gardez vos permissions au cas par cas.

## Lire avant d'installer

Une skill, un agent, un hook ou un plugin trouvé en ligne s'exécute chez vous. Lisez **tout le dossier**, pas seulement le SKILL.md ou le README : un paquet peut embarquer des scripts, des hooks ou un `.mcp.json`. La popularité et une licence MIT ne garantissent pas l'absence de script post-installation ou de connexion réseau cachée. Méfiez-vous aussi de la prompt injection : un CLAUDE.md ou un fichier tiers peut contenir des instructions qui pilotent Claude. Préférez les sources officielles et les dépôts maintenus. Voir l'étape [06. Plugins](parcours/06-plugins.md) et [skills.md](skills.md).

## MCP local n'est pas MCP confidentiel

Un serveur MCP, même local, transmet au modèle les données qu'il récupère, et un serveur tiers peut envoyer vos données vers un service externe. Deux questions avant de brancher :

> D'où vient ce serveur, et à quoi accède-t-il ? Local ne veut pas dire confidentiel : le modèle reçoit quand même ce que le serveur lui transmet.

Pour des données sensibles, privilégiez des serveurs que vous maîtrisez. Aligné sur l'étape [04. MCP](parcours/04-mcp.md).

## Relire les diffs avant de committer

Ne committez jamais en aveugle ce que Claude a produit. Relire le diff protège la qualité et la sécurité à la fois : un secret collé par mégarde, un fichier de trop, une dépendance inattendue. Voir [pieges-du-debutant.md](pieges-du-debutant.md).

## Mémo en cinq réflexes

- Autoriser au cas par cas, jamais tout d'un coup.
- Jamais de secret dans un fichier versionné ou un CLAUDE.md.
- Lire tout le dossier avant d'installer.
- Restreindre le champ `tools` au minimum nécessaire.
- Relire le diff avant de committer.

---

Pour le schéma de permissions à jour, voir [code.claude.com/docs](https://code.claude.com/docs/en/overview). Pour un audit ou un accompagnement encadré, c'est une prestation : [atelia-conseil.com](https://atelia-conseil.com).
