# Créer une instance et tester le template

> **S'adresse à :** mainteneur du template et personne qui crée son workspace.
>
> **Rôle :** créer un workspace personnel indépendant, le connecter au résident et vérifier le parcours `Hello Hermes` sans modifier le dépôt modèle.

## Modèle recommandé après publication

1. Ouvrir le dépôt public `HermesWorkspace-fr` sur GitHub.
2. Choisir **Use this template** / **Utiliser ce modèle**.
3. Créer un nouveau dépôt sous le compte de l'utilisatrice.
4. Choisir une visibilité privée par défaut.
5. Donner au dépôt un nom personnel, par exemple `MonWorkspace`.
6. Cloner ce nouveau dépôt sur la machine où Hermes réside.
7. Vérifier que `git remote get-url origin` désigne bien le dépôt privé de l'utilisatrice, pas le template public.

Une création depuis un template produit un dépôt indépendant. L'historique, les projets, la mémoire et les personnalisations appartiennent ensuite à l'utilisatrice.

## Où placer le clone

- Hermes résident sur un VPS : le clone principal doit être accessible dans son espace de travail sur le VPS.
- Hermes local : le clone principal se trouve sur la machine locale où l'agent s'exécute.
- Hermes Desktop connecté à un backend distant : Desktop est une télécommande ; le clone utile à l'agent reste celui du backend distant.
- Un clone supplémentaire sur l'ordinateur du propriétaire est facultatif pour consulter ou modifier le workspace manuellement.

Les chemins exacts dépendent de l'installation Hermes et ne sont volontairement pas imposés par ce template.

## Création manuelle si la fonction « Utiliser ce modèle » n'est pas disponible

Si le dépôt source n'est pas encore configuré comme template GitHub :

1. créer d'abord un dépôt privé vide sous le compte de l'utilisatrice ;
2. copier le contenu du template local sans son dossier `.git` ;
3. initialiser Git dans la copie ou pousser cette copie vers le dépôt privé ;
4. vérifier son remote `origin` avant de connecter Hermes ;
5. conserver le dossier local `HermesWorkspace-fr` séparé et intact.

Ne pas personnaliser directement le dépôt modèle local.

## Test de `Hello Hermes`

Depuis le dossier du workspace personnel, demander :

```text
Lis README.md et AGENTS.md, puis lance avec moi le parcours HELLO-HERMES.md.
Pose-moi les questions une par une et ne modifie aucun fichier avant mon accord final.
```

Le test est concluant si le résident :

- explique le but du parcours ;
- pose les questions progressivement ;
- propose des choix sans empêcher les réponses libres ;
- ne demande aucun secret ;
- marque comme non configurées les capacités non vérifiées ;
- ne modifie aucun fichier avant validation ;
- produit après validation une fiche résidente, un profil utilisateur et un SOUL de référence cohérents ;
- distingue le SOUL de référence du fichier réellement chargé par Hermes ;
- crée un premier projet de test au bon endroit ;
- n'active aucune GitHub App, tâche planifiée ou automatisation de sa propre initiative.

## Retour vers le template public

Noter les difficultés dans le suivi privé du pilote, sans donnée sensible. Une difficulté générique peut ensuite devenir une issue publique « Problème rencontré », « Idée d'amélioration » ou « Retour d'expérience ».

Les contenus personnels, chemins du VPS, configurations réelles, tokens et journaux contenant des informations privées ne doivent jamais être copiés dans le dépôt public.
