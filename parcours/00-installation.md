[Sommaire](../README.md) | Étape suivante : [01. CLAUDE.md](01-claude-md.md) →

# Étape 00. Installation

## Objectif

Installer Claude Code, le lancer dans un projet, et confirmer que tout est en place. Quinze minutes, montre en main.

## En clair

Claude Code est l'outil d'Anthropic qui fait travailler le modèle directement dans votre terminal, sur vos fichiers. Avant de coder quoi que ce soit, deux choses doivent être vraies : vous avez un abonnement compatible, et l'outil est installé.

Côté abonnement, il faut un compte **Pro, Max, Team, Enterprise** ou un accès **Console (API)**. Le plan gratuit de Claude.ai ne suffit pas. C'est le point qui surprend le plus de débutants.

## En pratique

La voie recommandée aujourd'hui est l'installeur natif (vérifié le 2026-06-22 sur la doc officielle).

macOS, Linux ou WSL :

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Windows, dans PowerShell :

```powershell
irm https://claude.ai/install.ps1 | iex
```

Autres voies officielles si vous préférez : `brew install --cask claude-code` sur macOS, `winget install Anthropic.ClaudeCode` sur Windows, ou via npm avec `npm install -g @anthropic-ai/claude-code` (Node.js 18 ou plus, sans `sudo`). Ces voies conviennent bien si vous préférez ne pas exécuter un script directement par un tube.

Si le terminal vous intimide, l'application Desktop (macOS et Windows) offre la même chose dans une fenêtre.

Ensuite, placez-vous dans un dossier de projet et lancez :

```bash
claude
```

Pour vérifier l'installation et la version :

```bash
claude doctor
claude --version
```

`claude doctor` est votre meilleur ami au démarrage : il diagnostique la plupart des soucis d'installation.

## Piège fréquent

Beaucoup de tutoriels plus anciens présentent npm comme la voie principale, avec une étape d'authentification par clé API à coller. Ce n'est plus la voie recommandée, et tenter de se connecter avec un plan gratuit mène à une impasse. Commencez par vérifier votre abonnement, puis utilisez l'installeur natif.

## Étape suivante

La référence à jour pour l'installation, tous systèmes confondus, est la page officielle : [code.claude.com/docs/en/setup](https://code.claude.com/docs/en/setup).

Une fois `claude` lancé, passez à l'étape suivante : donner du contexte à votre projet.

→ [01. CLAUDE.md](01-claude-md.md)
