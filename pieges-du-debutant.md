[Sommaire](README.md)

# Les pièges du débutant (et le bon réflexe)

Presque tout le monde tombe dans les mêmes pièges au départ. Les connaître fait gagner des semaines. Pour chacun : le symptôme, et le bon réflexe, avec un renvoi vers l'étape ou la page qui approfondit. Ce fichier complète [bonnes-pratiques.md](bonnes-pratiques.md) (les réflexes positifs) en regardant les choses par l'autre bout : les erreurs à éviter.

| Piège | Bon réflexe |
|---|---|
| Tout installer d'un coup | Partir d'un besoin réel, une chose à la fois |
| Créer dix agents le premier jour | Un ou deux agents utiles suffisent |
| Sur-ingénierie | Commencer petit et inoffensif |
| Faire confiance en aveugle | Relire les diffs, committer ciblé |
| Négliger le CLAUDE.md | Court, à jour, avec stack et conventions |
| Description vague | Préciser le quand |
| Demande trop grosse | Découper en petites tâches |
| Contexte saturé | `/clear` et `/compact` |
| Copier sans lire | Lire tout le dossier avant d'installer |
| Tout autoriser | Permissions au cas par cas |
| Vieux tutoriels | Vérifier sur la doc officielle |
| Confondre les briques | Choisir la bonne brique pour le besoin |

## Tout installer d'un coup

On découvre des dépôts avec 150 agents et 1000 skills, on installe tout, on ne comprend rien, on désinstalle. Partez d'un besoin réel et ajoutez une chose à la fois. Voir [bonnes-pratiques.md](bonnes-pratiques.md) et [07. Aller plus loin](parcours/07-aller-plus-loin.md).

## Créer dix agents le premier jour

C'est tentant, mais une collection qu'on n'utilise pas ajoute du bruit. Un ou deux agents qui servent vraiment suffisent. Voir [05. Subagents](parcours/05-subagents.md) et le [pack d'agents](agents/).

## Sur-ingénierie

Demander une usine là où une consigne suffit. Un hook qui relance un build complet à chaque caractère rend l'outil pénible. Commencez petit et inoffensif, complexifiez seulement si le besoin est réel. Voir [03. Hooks](parcours/03-hooks.md).

## Faire confiance en aveugle

Ne pas relire les diffs, committer ce qu'on n'a pas lu. Relisez les changements, committez ciblé, faites relire par un agent relecteur. Voir [bonnes-pratiques.md](bonnes-pratiques.md) et [securite-et-permissions.md](securite-et-permissions.md).

## Négliger le CLAUDE.md

Réexpliquer le projet à chaque session, ou au contraire bourrer un fichier de 300 lignes que Claude n'arrive plus à suivre. Visez un CLAUDE.md court, à jour, avec la stack, les commandes et les conventions. Voir [01. CLAUDE.md](parcours/01-claude-md.md).

## Description vague d'un skill ou d'un agent

Une description du genre « aide au code » ne se déclenche jamais au bon moment, car Claude ne sait pas quand l'utiliser. Précisez le quand. Voir [02. Commandes et skills](parcours/02-commandes-et-skills.md) et [05. Subagents](parcours/05-subagents.md).

## Demande trop grosse en un bloc

« Refais toute l'application » donne un résultat brouillon et difficile à relire. Découpez en petites tâches claires, validez au fur et à mesure. Voir [bonnes-pratiques.md](bonnes-pratiques.md).

## Contexte saturé

Une session qui mélange dix sujets dilue l'attention et coûte plus cher. Coupez avec `/clear` entre deux sujets sans rapport, compactez avec `/compact` quand une session utile s'allonge. Voir [bonnes-pratiques.md](bonnes-pratiques.md) et le [glossaire](glossaire.md).

## Copier un plugin ou un hook sans le lire

Un paquet copié tel quel s'exécute chez vous, avec vos droits. Lisez tout le dossier avant d'installer, préférez les sources officielles et maintenues. Voir [securite-et-permissions.md](securite-et-permissions.md), l'étape [06. Plugins](parcours/06-plugins.md) et [skills.md](skills.md).

## Tout autoriser

Cliquer « autoriser » partout, ou lancer un mode qui contourne les validations, laisse passer une commande risquée. Gardez les permissions au cas par cas. Voir [securite-et-permissions.md](securite-et-permissions.md).

## Suivre de vieux tutoriels

Beaucoup de tutoriels datent : ils présentent les commandes et les skills comme deux choses séparées, ou copient une syntaxe qui a changé. La documentation officielle fait autorité : [code.claude.com/docs](https://code.claude.com/docs/en/overview). Voir l'étape [02. Commandes et skills](parcours/02-commandes-et-skills.md).

## Confondre les briques

Tout faire en plugin, ou tout en agent, parce qu'on ne sait pas laquelle choisir. Voir [Quelle brique pour quel besoin ?](choisir-skill-subagent-mcp-plugin.md).

---

Ces pièges se désamorcent vite une fois nommés. Un piège manque ? Proposez-le via [CONTRIBUTING.md](CONTRIBUTING.md). Pour un accompagnement encadré, c'est une prestation : [atelia-conseil.com](https://atelia-conseil.com).
