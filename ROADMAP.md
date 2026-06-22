[Sommaire](README.md)

# Feuille de route

Ce dépôt est vivant. Voici ce qui est livré, ce qui vient ensuite, et ce qu'on refuse volontairement de faire pour rester soutenable et fidèle à sa promesse : un repère clair, à jour, vérifié.

## Livré

- [x] Le parcours en 7 étapes (installation au premier plugin).
- [x] Un starter prêt à cloner (`exemple-starter/`).
- [x] Un pack de 6 subagents en français (`agents/`).
- [x] Une sélection de skills publiques vérifiées (`skills.md`).
- [x] Les bonnes pratiques (`bonnes-pratiques.md`).
- [x] Un annuaire des ressources (`ressources.md`).
- [x] **L'annuaire par domaine** (`annuaire-par-domaine.md`), les ressources classées par usage.
- [x] **Le glossaire** (`glossaire.md`), les termes clés définis simplement.
- [x] **La FAQ des erreurs fréquentes** (`faq-erreurs-frequentes.md`).

## En cours et à venir

Par ordre de priorité.

- [ ] **Aide-mémoire (cheatsheet)** des commandes, raccourcis et gestes, vérifiés sur la doc officielle, avec les équivalents Windows et PowerShell. Priorité haute, valeur immédiate.
- [ ] **« Quelle brique pour quel besoin ? »** un arbre de décision (skill, commande, subagent, hook, MCP, plugin). Lève la confusion numéro un du débutant. Priorité haute.
- [ ] **Sécurité et permissions** : une page dédiée pour ne pas se faire mal (permissions, secrets, lire avant d'installer). Priorité haute.
- [ ] **Les pièges du débutant** : un catalogue des erreurs classiques et du bon réflexe. Priorité haute.
- [ ] **Badge « vérifié le JJ/MM/AAAA »** visible en tête de chaque fichier de ressources, mis à jour à chaque passe de fraîcheur. Priorité haute, effort faible.
- [ ] **Sélection de plugins par métier** (dev web, data et IA, no-code, rédaction) dérivée de l'annuaire, sans le dupliquer. Priorité moyenne.
- [ ] **Schéma de l'arbre de décision** en Mermaid (rendu natif sur GitHub, maintenance quasi nulle). Priorité moyenne.
- [ ] **Traduction anglaise du README** (`README.en.md`) en miroir, en gardant le parcours en français dans un premier temps. Priorité moyenne.
- [ ] **Captures et exemples animés** pour les étapes les plus stables seulement (une capture périmée est pire que pas de capture). Priorité moyenne, effort élevé.
- [ ] **Modèle d'issue** « signaler un lien mort ou un dépôt abandonné », pour canaliser les contributions vers le plus utile. Priorité basse.

## Fraîcheur : comment on tient la promesse

La fraîcheur est l'argument de ce dépôt (vérifié en direct, zéro chiffre inventé). On la tient avec une passe **trimestrielle** (quatre fois par an), pas plus, pour que ce soit réellement fait plutôt qu'ambitieux et abandonné.

Le mécanisme reste simple et local :

1. Un petit script local lit les couples `owner/name` cités dans `ressources.md`, `skills.md` et l'annuaire, interroge l'API GitHub publique (sans token) pour chacun, et produit un rapport : étoiles, statut archivé, date du dernier push.
2. Le script signale trois alertes : dépôt introuvable (lien mort), dépôt archivé (abandonné), dernier push de plus de six mois (à requalifier à la main).
3. Vérification des liens hors GitHub par un simple appel HTTP.
4. Mise à jour éditoriale à la main : requalifier les statuts, ajuster les ordres de grandeur, et changer la date du badge, puis committer.

Le script est un outil de détection en lecture seule. Il ne réécrit jamais le contenu : le jugement éditorial reste humain.

## Ce qu'on ne fera pas (volontairement)

Le vrai risque d'un dépôt maintenu seul n'est pas le manque d'idées, c'est la dette de maintenance. On refuse donc :

- le scraping automatique massif d'autres listes pour gonfler l'annuaire ;
- la traduction complète et permanente de tout le parcours en plusieurs langues ;
- le catalogue exhaustif des centaines de plugins existants.

On garde un repère sélectif, ordonné et soutenable. Pour la profondeur et le volume, ce sont les grands catalogues qui font le travail, et ils sont cités.

---

Une idée, une correction ? Voir [CONTRIBUTING.md](CONTRIBUTING.md).
