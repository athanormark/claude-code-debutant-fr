[Sommaire](README.md)

# Bonnes pratiques

Quelques réflexes qui font la différence entre subir Claude Code et en tirer un vrai gain. Rien d'avancé ici : ce sont les habitudes qui évitent les ennuis les plus courants.

## Donner du contexte, pas des consignes répétées

Un bon `CLAUDE.md` court vaut mieux que de réexpliquer votre projet à chaque session. Stack, commandes, conventions, pièges connus. Tenez-le à jour, gardez-le bref (voir l'étape [01](parcours/01-claude-md.md)).

## Découper le travail

Une demande énorme (« refais toute l'application ») donne un résultat flou et difficile à relire. Avancez par petites tâches claires, validez au fur et à mesure. Vous gardez le contrôle et vous comprenez ce qui change.

## Garder le contexte propre

Une longue session accumule du contexte, ce qui dilue l'attention et coûte plus cher. Utilisez `/clear` entre deux sujets sans rapport, et `/compact` quand une session utile devient longue.

## Ne pas tout autoriser

La facilité est de cliquer « autoriser » partout, voire de désactiver les permissions. C'est aussi le meilleur moyen de laisser passer une commande destructrice. Accordez les permissions au cas par cas, et méfiez-vous des options qui contournent les garde-fous.

## Lire avant d'exécuter, lire avant d'installer

Une skill, un agent, un hook ou un plugin trouvés en ligne s'exécutent sur votre machine, avec vos droits. Prenez trente secondes pour les lire. Vous savez maintenant le faire. Préférez les sources officielles et les dépôts maintenus.

## Relire avant de committer

Faites relire les changements (un agent relecteur fait très bien le travail, voir le [pack d'agents](agents/)). Committez des changements ciblés, avec un message clair, plutôt qu'un gros lot fourre-tout.

## Versionner ce qui se partage, garder le perso en local

Le `CLAUDE.md` et le `.claude/settings.json` du projet se versionnent et se partagent avec l'équipe. Vos réglages personnels vont dans `.claude/settings.local.json`, qui ne se committe pas. Pensez à l'ajouter au `.gitignore`.

## Protéger vos données

Tout ne doit pas sortir de chez vous. Pour des données sensibles, privilégiez des serveurs MCP locaux ou que vous maîtrisez, et réfléchissez à ce qu'un outil externe peut voir avant de le brancher. Gardez en tête que local ne veut pas dire confidentiel : le modèle reçoit quand même les données que l'outil lui transmet.

## Itérer

Le premier jet n'est pas le dernier. Faites un prototype, regardez le résultat, ajustez vos consignes. Claude Code est un outil que vous apprenez à diriger, pas une boîte magique.
