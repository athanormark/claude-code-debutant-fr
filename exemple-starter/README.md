[Sommaire](../README.md)

# Starter minimal

Une configuration `.claude/` de départ, générique et volontairement simple. Copiez ce dossier à la racine d'un projet pour partir d'une base saine plutôt que d'une page blanche.

## Contenu

```
exemple-starter/
  CLAUDE.md                      La mémoire du projet (à personnaliser)
  .claude/
    settings.json                Réglages prudents (permissions d'exemple)
    skills/
      message-de-commit/
        SKILL.md                 Un skill qui rédige un message de commit
    agents/
      relecteur-code.md          Un subagent relecteur, en lecture seule
```

## Comment s'en servir

1. Copiez `CLAUDE.md` et le dossier `.claude/` à la racine de votre projet.
2. Ouvrez `CLAUDE.md` et remplacez les éléments entre parenthèses par votre réalité (stack, commandes, conventions).
3. Lancez `claude`, puis essayez `/message-de-commit` et une demande de relecture.

## Important

Les exemples sont des **points de départ à adapter**, pas des vérités gravées. En particulier, la syntaxe des permissions et des hooks évolue : vérifiez toujours la forme à jour sur la [documentation officielle](https://code.claude.com/docs/en/overview) avant de vous appuyer dessus.

Le `deny` du `settings.json` est seulement illustratif : il bloque un exemple de commande, pas toutes les manières de supprimer des fichiers. Ne le prenez pas pour une protection complète.

Le fichier `.claude/settings.local.json` (vos réglages personnels) ne doit pas être committé. Le `.gitignore` à la racine du dépôt l'ignore déjà.
