# Installation et démarrage du workspace

> **S'adresse à :** personne qui crée une instance depuis le template, puis résident lors de sa première session.
>
> **Rôle :** personnaliser avec le résident une instance déjà créée et accessible. La création du dépôt personnel et de son clone est décrite dans `_guides/07-pilote-et-instance.md`.

Avant de commencer, créer une instance indépendante selon `_guides/07-pilote-et-instance.md`. Ne pas personnaliser directement le dépôt modèle public ou sa copie source locale.

## Pour le propriétaire

1. Créer un dépôt personnel à partir de ce modèle, privé par défaut.
2. Donner au résident un accès en lecture au workspace selon son installation.
3. Lui demander de conduire le parcours `HELLO-HERMES.md`.
4. Valider son récapitulatif avant toute modification.
5. Créer `agents/resident.md`, `SOUL.md` et personnaliser `USER.md` à partir des réponses validées.
6. Remplacer le responsable dans `AI-HANDOFF.md` et `.github/MAINTAINERS.md`.
7. Déployer le contenu de `SOUL.md` vers l'emplacement réellement chargé par Hermes si cette opération reste à la charge du propriétaire.
8. Vérifier les placeholders : ceux des fichiers actifs de l'instance doivent être remplis ; ceux des fichiers `.example.md` et de `projects/_template/` peuvent rester comme modèles.
9. Lui demander d'effectuer la première session ci-dessous.

## Première session du résident

Le résident doit :

1. lire `AGENTS.md` et sa fiche ;
2. lire `USER.md`, `MEMORY.md` et `AI-HANDOFF.md` ;
3. reformuler son rôle, ses limites et ses capacités vérifiées ;
4. signaler les placeholders oubliés ;
5. créer un premier projet de test depuis `projects/_template/` ;
6. produire un petit brouillon dans `work/` ;
7. proposer, sans l'inventer, le premier fait réellement durable à mémoriser ;
8. effectuer un commit de test si Git fait partie de ses capacités.

Ne pas configurer de GitHub App, de tâche planifiée ou d'autre automatisation avant que ce fonctionnement de base soit compris.
