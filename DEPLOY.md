# Déploiement des applications Ma carte

Sauf indication contraire toutes les applications (hors API) se déploient de la même façon.

## Déploiement sur l'instance de test (Gitlab.io)

Il est nécessaire de faire un build avant de faire un commit sur Gitlab.   
C'est le résultat du build qui sera déployé.   
La commande de build va générer le code dans le répertoire `./docs` du projet (qui servira d'artifact à l'intégration en continue)

Avant de lancer le build, lancer une analyse statique du code source et corrigez les problèmes remontés (`npm run lint`).

```
npm run build
```

NB: il est parfois nécessaire de vider manuellement le répertoire public avant de lancer la commande pour supprimer les fichiers obsolètes.

## Déploiement

### Créer l'image docker

- A la racine du projet, lancer la commande 

```bash
docker build . -f ./Dockerfile -t macarte_storymap
```

- Entrer dans l'image Docker (ligne de commande)

```bash
docker run -it macarte_storymap bash
```

### Activer les images

- Activer l'application et la base de données

```bash
sudo docker compose up -d
```

Le site est sur ```localhost:8088```

- Stopper l'image

```bash
sudo docker compose stop
```

- Vérifier l'état des images

```bash
docker compose ps
```

- Vérifier les logs de l'image

```bash
docker logs naviforest-app-1 #nom de l'image
``` 

- Supprimer les images

```bash
docker compose down
```
