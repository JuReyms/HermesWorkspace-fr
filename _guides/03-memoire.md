# Stratégie de mémoire

> **S'adresse à :** propriétaire et tous les agents de l'instance.
>
> **Rôle :** choisir le bon emplacement pour chaque fait sans encombrer la mémoire globale.

## Les niveaux

- `USER.md` : profil et préférences durables du propriétaire.
- `MEMORY.md` : faits communs utiles à tous les agents.
- Mémoire native : faits propres au résident et toujours utiles à ses sessions.
- `projects/<projet>/memory/` : connaissance durable propre à un projet.
- Historique des sessions : faits conversationnels à rechercher à la demande, si l'outil existe.
- Skills : procédures réutilisables, si l'installation les prend en charge.

## Règle de placement

Demander : « Qui doit connaître ce fait, et dans quel contexte ? »

Un fait projet ne va pas dans la mémoire globale. Une préférence commune ne reste pas enfermée dans la mémoire native du résident. Une procédure ne doit pas devenir une longue note de mémoire.

La mémoire doit rester courte, exacte, non sensible et régulièrement nettoyée.
