# Sécurité et confidentialité

> **S'adresse à :** propriétaire, résident et invités.
>
> **Rôle :** définir ce qui peut entrer dans le workspace et ce qui peut circuler entre contextes.

## Règle de base

Tout contenu lu par un agent cloud peut être transmis à son fournisseur. Le workspace contient donc uniquement ce que le propriétaire accepte de faire traiter par les agents autorisés.

Ne jamais déposer ici :

- mots de passe, tokens, clés API ou clés SSH ;
- documents bancaires, médicaux ou administratifs privés ;
- exports complets de messagerie ;
- configurations révélant inutilement une infrastructure ;
- données confidentielles de tiers.

Les secrets vont dans un gestionnaire de secrets. Les documents sensibles restent hors de tout workspace accessible aux agents.

## Circulation de l'information

Lire une information ne donne pas le droit de la recopier. Un agent qui intervient aussi sur un hôte, un VPS ou un autre dépôt doit conserver la séparation entre ces contextes.

Une conclusion générique peut être transmise si elle ne révèle rien de protégé. En cas de doute, demander au propriétaire.
