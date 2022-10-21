# release pipeline

## Description

La pipeline transforme le code en image docker optimisée (grâce au multistaging).

L'image peut ensuite être récupérée depuis la liste des packages, sur la page principale du répo.

## Utilisation

- [ ] Importez la pipeline dans votre répo, depuis l'interface github.
- [ ] Créez un Dockerfile à la racine de votre répo.
  - NB : Il est important d'utiliser le **multistage** pour ne pas générer d'image trop grosse !
    - Stage 1 qui build l'app
    - Stage 2 qui la passe dans une image alpine
    - N'hésitez pas à regarder le Dockerfile du répo "ms-template" pour vous aider

### Triggers

- L'image sera générée à chaque push sur la branche release. Elle prendra automatiquement le tag de la version.
- Elle peut aussi être générée manuellement, depuis l'interface github.

### Téléchargement

Pour récupérer l'image, rendez-vous sur la page principale du répo, dans la section "Packages".
Vous pourrez vois le lien de téléchargement de l'image.

> NB : vous devrez être authentifié pour pouvoir télécharger l'image !

#### Credentiels

Créez un token github dans votre profil/settings/tokens avec les droits suivants :

- repo
- packages:read
- packages:write

Ajoutez les crédentiels à votre machine :

```bash
docker login ghcr.io -u <nom utilisateur> -p <token>
```

#### Pull

```bash
docker pull ghcr.io/discoverio/< nom repo >:< tag >
```