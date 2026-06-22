[Sommaire](../README.md)

# Pack d'agents à adopter

Une petite collection de subagents prêts à l'emploi, génériques et utiles dès le premier jour. Choisissez ceux qui vous parlent, copiez-les chez vous, adaptez-les.

Pour comprendre ce qu'est un subagent, voir l'étape [05. Subagents](../parcours/05-subagents.md) du parcours.

## Les agents disponibles

| Fichier | Rôle | Outils |
|---|---|---|
| [relecteur-code.md](relecteur-code.md) | Relit le code modifié, signale bugs et risques | lecture seule |
| [explorateur-code.md](explorateur-code.md) | Explore et explique une base de code inconnue | lecture seule |
| [redacteur-tests.md](redacteur-tests.md) | Écrit des tests pour du code existant | lecture et écriture |
| [debogueur.md](debogueur.md) | Traque un bug par la méthode scientifique | lecture, écriture, exécution |
| [documentaliste.md](documentaliste.md) | Rédige et met à jour la documentation | lecture et écriture |
| [refactoreur.md](refactoreur.md) | Simplifie sans changer le comportement | lecture et écriture |

## Comment se les attribuer

Un subagent est un simple fichier Markdown. Pour l'adopter, copiez-le à l'un de ces endroits :

- `.claude/agents/` à la racine de votre projet : l'agent vit avec ce projet, et vous pouvez le partager avec votre équipe.
- `~/.claude/agents/` : l'agent vous suit sur tous vos projets.

Exemple, depuis ce dépôt :

```bash
mkdir -p ~/.claude/agents
cp agents/relecteur-code.md ~/.claude/agents/
```

Relancez `claude`. L'agent est disponible. Claude le déclenche tout seul quand votre demande correspond à sa `description`, et vous pouvez aussi le solliciter explicitement (par exemple : « relis mes derniers changements »).

## Avant d'adopter un agent

- **Lisez-le.** Vous savez maintenant lire un fichier d'agent : faites-le, c'est court.
- **Ajustez les outils.** Le champ `tools` limite ce que l'agent peut faire. Élargissez seulement si nécessaire.
- **Attention aux outils puissants.** Un agent qui a `Bash` ou `Write` (comme `debogueur` ou `redacteur-tests`) peut exécuter des commandes et modifier votre machine. Faites-le tourner d'abord sur un projet de test, et gardez vos permissions au cas par cas.
- **Lecture seule ne veut pas dire confidentiel.** Même limité à `Read, Grep, Glob`, un agent peut lire des fichiers sensibles (`.env`, clés). Pensez à un `permissions.deny` sur ces fichiers.
- **Adaptez le prompt** à votre contexte (langage, conventions de votre projet).

Ces agents sont des points de départ sous licence MIT. Modifiez-les sans réserve.
