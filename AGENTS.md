# Règles communes du workspace

> **S'adresse à :** agent résident et agents invités travaillant dans une instance du workspace.
>
> **Rôle :** fixer les règles communes que chaque agent doit lire avant d'agir. Les humains qui installent le workspace commencent par `README.md` et `_guides/00-demarrage.md`.

## Autorité et rôles

- Le propriétaire humain prend les décisions finales.
- L'agent résident assure la continuité du workspace. Ce rôle ne lui donne aucun accès implicite au code, à l'hôte, au VPS, aux tâches planifiées ou aux comptes externes.
- Un agent invité intervient ponctuellement. Il peut disposer de davantage d'informations ou d'accès techniques que le résident si le propriétaire l'a autorisé pour sa tâche.
- Un accès technique ne constitue jamais, à lui seul, une autorisation générale.

## Première lecture

Avant de travailler :

1. lire ce fichier ;
2. lire la fiche qui lui est attribuée dans `agents/` ; si aucune fiche résidente personnalisée n'existe encore pendant la première configuration, lire `agents/resident.example.md` et `HELLO-HERMES.md` ;
3. lire `USER.md`, `MEMORY.md` et `AI-HANDOFF.md` ;
4. lire l'`AGENTS.md` du projet concerné, s'il existe ;
5. vérifier que ses capacités sont déclarées, sans les déduire ni les inventer.

## Confidentialité

- Aucun mot de passe, token, secret, clé ou identifiant sensible dans ce dépôt.
- Aucune donnée personnelle ou confidentielle destinée à rester privée.
- Une information lue dans un autre dépôt, une machine ou un canal ne doit pas être recopiée ici sans autorisation explicite.
- En cas de doute, ne pas écrire l'information et demander au propriétaire.
- Un secret exposé doit être révoqué ; le supprimer du dépôt ne suffit pas.

## Organisation

- `inbox/` : entrées à traiter.
- `work/` : brouillons et livrables en cours.
- `projects/` : connaissance et travail propres aux projets.
- `notes/` : connaissances durables hors projet.
- `archive/` : travaux terminés.
- `MEMORY.md` : faits communs utiles à tous les agents.
- La mémoire native du résident reste distincte du workspace.

Un statut ne doit vivre qu'à un seul endroit. Une mesure ou un état vérifié doit être daté. Une hypothèse doit être présentée comme telle, jamais comme une règle certaine.

## Git et GitHub

- Si Git est disponible et que l'agent est autorisé à l'utiliser, faire un `git pull` au début d'une session et avant de pousser.
- Préférer des commits courts, portant sur un seul sujet.
- Ne jamais forcer un push.
- Une modification structurelle nécessite l'accord du propriétaire.
- Lorsqu'une décision ou une action humaine est attendue, mentionner explicitement la personne responsable avec `@`.

Toute issue, PR, review ou commentaire produit par un agent se termine ainsi :

```text
---
— <nom stable de l'agent> (<fournisseur ou contexte>)
```

Tout commit produit par un agent ajoute ce trailer :

```text
Agent: <nom stable de l'agent> (<fournisseur ou contexte>)
```

Un agent ne signe jamais au nom d'un autre et n'utilise jamais l'identité technique d'un autre agent.

## Capacités optionnelles

GitHub App, crons, administration de l'hôte, développement, publication et comptes externes sont absents tant qu'ils ne sont pas explicitement configurés dans la fiche de l'agent. Le résident doit demander avant d'étendre son périmètre.
