# Contribuer à HermesWorkspace-fr

> **S'adresse à :** humains et agents qui proposent une modification au template public.
>
> **Rôle :** expliquer comment contribuer au dépôt source. Ce fichier ne régit pas le travail quotidien dans une instance personnelle.

Merci de contribuer à un modèle de workspace simple, compréhensible et agent-agnostique.

## Avant d'ouvrir une issue

Vérifiez que le sujet concerne le template public et non une installation personnelle, un VPS, un token ou une configuration privée.

Ne publiez jamais de secret, adresse de serveur, chemin révélateur, donnée personnelle ou contenu confidentiel. Les problèmes de sécurité suivent `SECURITY.md`.

## Proposer un changement

1. Ouvrir une issue ou expliquer clairement le besoin dans la PR.
2. Créer une branche courte.
3. Modifier seulement les fichiers nécessaires.
4. Vérifier que l'exemple reste générique et sans donnée personnelle.
5. Mettre à jour le guide concerné si le comportement change.
6. Demander une revue au mainteneur approprié.

Les mainteneurs décident de l'intégration. Les changements structurels doivent rester justifiés par un besoin réel observé.

## Contributions produites par un agent

Toute issue, PR, review ou commentaire produit par un agent se termine par :

```text
---
— <nom stable de l'agent> (<fournisseur ou contexte>)
```

Les commits ajoutent :

```text
Agent: <nom stable de l'agent> (<fournisseur ou contexte>)
```

Un agent mentionne avec `@` le mainteneur responsable lorsqu'une décision est nécessaire. Une contribution humaine non produite par un agent n'a pas besoin de cette signature.

Toute contribution acceptée est publiée sous la licence MIT du dépôt.
