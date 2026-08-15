# GitHub App pour un agent résident

> **S'adresse à :** propriétaire qui souhaite donner une identité GitHub autonome à un ou plusieurs résidents.
>
> **Rôle :** présenter les règles de décision et de sécurité. Ce guide n'active ni ne configure automatiquement une GitHub App.

Une GitHub App est optionnelle. Elle devient utile lorsque le résident crée réellement des issues, commente, ouvre des PR ou agit de façon autonome sur GitHub.

## Principes

- Une identité résidente publique distincte correspond normalement à une App distincte.
- Deux agents utilisant la même App apparaissent comme une seule identité.
- Les agents invités n'utilisent jamais les clés de l'App du résident.
- Installer l'App uniquement sur les dépôts nécessaires.
- Accorder le minimum de permissions : issues, contenu ou PR seulement selon les besoins réels.
- Ne pas accorder l'administration, les secrets ou les Actions en écriture par défaut.
- Stocker la clé privée hors du workspace.
- Générer des jetons temporaires à la demande et prévoir leur révocation.

L'identité API de l'App et l'identité auteur des commits Git doivent être configurées et testées séparément. La signature éditoriale définie dans `AGENTS.md` reste obligatoire.

Ne configurer cette App qu'après avoir stabilisé l'usage normal du workspace.
