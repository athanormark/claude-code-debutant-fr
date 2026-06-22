[Sommaire](README.md)

# Les meilleures skills, et où les trouver

Une fois que vous savez créer une skill (voir l'étape [02. Commandes et skills](parcours/02-commandes-et-skills.md)), le réflexe utile est de ne pas tout réinventer. Voici une sélection de sources publiques qui valent le détour, avec leur dépôt source.

> **Fraîcheur.** Dépôts et chiffres vérifiés le **2026-06-22**. Les étoiles sont des ordres de grandeur, elles bougent vite.
>
> **Sécurité.** Avant d'installer, lisez tout le dossier, pas seulement le `SKILL.md` : un paquet peut embarquer des scripts, des hooks ou un `.mcp.json` qui s'exécutent chez vous. Testez sur un projet jetable avant de l'installer pour tous vos projets dans `~/.claude/`.

## La sélection

### obra/superpowers
Un cadre de skills et une méthode de développement très complets : brainstorming, développement piloté par les tests, débogage systématique, vérification avant livraison, écriture de plans. C'est l'une des collections les plus suivies de l'écosystème. À savoir : c'est un plugin qui installe aussi des hooks de démarrage de session et une télémétrie de version optionnelle (désactivable). Raison de plus pour lire avant d'installer.
- Dépôt : [github.com/obra/superpowers](https://github.com/obra/superpowers)
- Repère (2026-06-22) : ~236 000 étoiles, très actif.
- Pour qui débute : commencez par les skills de méthode (planifier, déboguer pas à pas), ce sont celles qui changent le plus la donne.

### anthropics/skills
Le dépôt officiel des Agent Skills. On y trouve notamment les skills documents (Word, PowerPoint, PDF, Excel) et de quoi créer vos propres skills proprement. Les licences varient d'une skill à l'autre (certaines skills documents sont en source-available, pas en open source) : vérifiez la licence avant un usage commercial.
- Dépôt : [github.com/anthropics/skills](https://github.com/anthropics/skills)
- Repère (2026-06-22) : ~154 000 étoiles, actif. Suit le standard ouvert [agentskills.io](https://agentskills.io).

### wshobson/agents
Un grand marketplace qui réunit skills, agents et commandes. Pratique pour piocher une skill précise une fois qu'on sait ce qu'on cherche.
- Dépôt : [github.com/wshobson/agents](https://github.com/wshobson/agents)
- Repère (2026-06-22) : ~37 000 étoiles, très actif.
- À savoir : c'est un marketplace multi-outils (Claude Code, mais aussi Codex, Cursor, etc.). Vérifiez la compatibilité de ce que vous installez.

### pedronauck/skills
Une sélection personnelle et soignée de skills, plus resserrée que les gros catalogues. Utile pour découvrir des idées sans se noyer.
- Dépôt : [github.com/pedronauck/skills](https://github.com/pedronauck/skills)
- Repère (2026-06-22) : ~435 étoiles, actif.

## Comment en installer une

En bref : déposez le dossier de la skill dans `.claude/skills/` (pour le projet) ou `~/.claude/skills/` (pour vous, partout). Elle est détectée automatiquement et s'invoque avec `/nom-de-la-skill`. Le détail est dans l'étape [02. Commandes et skills](parcours/02-commandes-et-skills.md).

## Pour aller plus loin

Pour les listes exhaustives (et leurs avertissements de périmètre), voir l'[annuaire des ressources](ressources.md), qui recense aussi les grandes awesome-lists.
