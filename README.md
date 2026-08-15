# HermesWorkspace-fr

Un modèle de workspace francophone pour organiser la collaboration entre un propriétaire humain, un agent résident et des agents invités.

Pensé à partir d'un usage avec Hermes Agent, il reste compatible avec tout agent capable de lire et respecter un fichier `AGENTS.md`.

Projet communautaire indépendant : ce dépôt n'est ni un composant officiel de Hermes Agent, ni affilié à Nous Research.

## Principes

- Le propriétaire humain reste l'autorité finale.
- « Résident » décrit la continuité, pas le niveau d'accès.
- Chaque agent possède un périmètre explicite et n'invente jamais ses capacités.
- Le workspace ne contient ni secret ni donnée sensible.
- Les faits communs, la mémoire propre à l'agent et le savoir projet restent séparés.
- Toute écriture GitHub produite par un agent identifie son auteur réel.

## Architecture du workspace

```text
HermesWorkspace-fr/
├── AGENTS.md          règles communes lues par tous les agents
├── USER.md            profil et préférences durables du propriétaire
├── MEMORY.md          mémoire commune à tous les agents
├── AI-HANDOFF.md      coordination courante de cette instance du workspace
├── HELLO-HERMES.md    conversation guidée de première configuration
├── SOUL.example.md    modèle à copier vers la référence SOUL de l'instance
├── agents/            modèles et fiches des agents de cette instance
├── _guides/           modes d'emploi du workspace
├── inbox/             nouvelles entrées à traiter
├── work/              brouillons et livrables transversaux en cours
├── projects/          contexte, mémoire et travail propres aux projets
├── notes/             connaissances durables hors projet
├── archive/           travaux terminés
└── .github/           contribution, issues et pull requests
```

Le fonctionnement repose sur trois niveaux complémentaires :

- **Racine** : identité du propriétaire, mémoire commune, règles et travail courant.
- **`agents/`** : rôle réel de chaque agent, indépendamment de ses accès techniques.
- **`projects/`** : contexte durable isolé par projet, avec ses propres instructions et brouillons.

Lorsqu'un agent commence une session, il lit les règles et le contexte courant. Il traite ensuite les entrées dans `inbox/`, travaille dans `work/` ou dans le dossier du projet concerné, puis range ce qui devient durable dans `projects/` ou `notes/`.

## Qui lit quoi ?

Ce dépôt est conçu pour plusieurs points de vue :

| Lecteur | Commence par | Utilise ensuite |
|---|---|---|
| Personne qui installe le workspace | `README.md` | `_guides/00-demarrage.md`, puis `HELLO-HERMES.md` avec le résident |
| Agent résident | `AGENTS.md` | sa fiche personnalisée dans `agents/`, `USER.md`, `MEMORY.md`, `AI-HANDOFF.md`, puis le projet concerné |
| Agent invité | `AGENTS.md` | `agents/guests.md`, `AI-HANDOFF.md`, puis les instructions du projet concerné |
| Contributeur au template public | `CONTRIBUTING.md` | `CHANGELOG.md`, `SECURITY.md` et les issues du dépôt source |

`AI-HANDOFF.md` décrit uniquement le travail courant dans **l'instance personnelle** du workspace : sujet actif, responsable, décision attendue et prochaine action. La conception et la roadmap interne du template ne sont pas distribuées dans les instances.

Le dépôt public ne contient aucune fiche personnelle de ses créateurs ou contributeurs. Dans une instance privée, le propriétaire crée `agents/resident.md` pour son résident et peut ajouter `agents/<nom>.md` pour un invité récurrent. Un invité ponctuel suit simplement `agents/guests.md` et signe ses contributions.

## Du template public au workspace personnel

Le dépôt public est un modèle commun : il ne devient pas directement le workspace personnel de l'utilisateur.

```text
HermesWorkspace-fr public
          │
          └── Utiliser ce modèle
                    │
                    ▼
       dépôt privé de l'utilisateur
             ├── clone sur le VPS où réside Hermes
             └── clone facultatif sur son ordinateur
```

Le dépôt privé appartient à l'utilisateur et son remote `origin` pointe vers ce dépôt. Le résident travaille dans le clone présent sur la machine où il s'exécute — généralement le VPS pour un Hermes distant. Le clone sur l'ordinateur personnel est facultatif et sert à consulter ou modifier les mêmes fichiers manuellement.

Les améliorations futures du template public ne sont jamais appliquées automatiquement au workspace privé. Elles sont consultées dans le dépôt source canonique, puis reprises volontairement si elles sont utiles.

> **Dépôt source canonique :** <https://github.com/JuReyms/HermesWorkspace-fr>

## Hello Hermes : la première conversation

`HELLO-HERMES.md` est le parcours de bienvenue utilisé une seule fois lors de la création d'une instance. Il permet au résident de découvrir progressivement :

- comment appeler son propriétaire et communiquer avec lui ;
- son propre nom, son ton et son rôle ;
- les premiers usages attendus ;
- ses accès réellement configurés et ses interdictions ;
- les règles de confidentialité et de validation ;
- la manière de collaborer avec d'éventuels agents invités.

Pour le lancer, ouvrez une première conversation avec le résident depuis le dossier du workspace et envoyez simplement :

```text
Lis README.md et AGENTS.md, puis lance avec moi le parcours HELLO-HERMES.md.
Pose-moi les questions une par une et ne modifie aucun fichier avant mon accord final.
```

Le résident ne doit demander aucun secret. À la fin, il présente un récapitulatif et propose la personnalisation de `USER.md`, de `agents/resident.md`, d'un `SOUL.md` de référence et du premier projet de test. Les fichiers ne sont modifiés qu'après validation du propriétaire. Si Hermes charge son SOUL depuis un emplacement extérieur au workspace, le résident fournit le contenu validé mais ne suppose pas qu'il peut le déployer lui-même.

Pour rendre l'échange plus simple, il peut proposer deux ou trois réponses courantes sous forme de choix multiples, avec une option recommandée et une courte explication. Le propriétaire peut toujours répondre librement ou décider plus tard.

## Installer une instance du workspace

### Prérequis

- Hermes — ou un autre agent compatible — est déjà installé et fonctionne.
- L'agent peut lire un dossier de travail sur la machine où il s'exécute.
- Pour la synchronisation et la collaboration : Git et un compte GitHub sont disponibles.

Ce dépôt n'installe ni Hermes, ni Git, ni le VPS. Il organise le workspace une fois ces éléments disponibles.

1. Utilisez ce dépôt comme modèle pour créer de préférence un dépôt privé.
2. Suivez [`_guides/07-pilote-et-instance.md`](_guides/07-pilote-et-instance.md) pour créer le dépôt personnel et placer son clone au bon endroit.
3. Suivez [`_guides/00-demarrage.md`](_guides/00-demarrage.md) pour personnaliser l'instance avec le résident.
4. Lancez avec lui le parcours de bienvenue `HELLO-HERMES.md`.
5. Validez ses propositions avant qu'il crée ou personnalise les fichiers de votre instance.
6. Vérifiez ensuite qu'aucun placeholder `A_REMPLIR` ne subsiste dans les fichiers actifs de l'instance.

Le serveur, Docker, les clés API et l'installation de Hermes ne font volontairement pas partie de ce dépôt. Ils relèvent d'un guide d'infrastructure séparé.

## Flux de travail

```text
inbox → work → projects/notes → archive
```

## Version du template

Version initiale de travail `v0.1`. Les changements publiés sont consignés dans [`CHANGELOG.md`](CHANGELOG.md). La roadmap interne de maintenance n'est volontairement pas incluse dans les instances.

Pour créer une instance sans modifier le dépôt modèle, suivre [`_guides/07-pilote-et-instance.md`](_guides/07-pilote-et-instance.md).
