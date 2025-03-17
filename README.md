# 🛠 Commandes Docker et Docker Compose

## 🚀 Gestion des Conteneurs
```sh
docker ps                     # Liste les conteneurs en cours d'exécution
docker ps -a                  # Liste tous les conteneurs (même arrêtés)
docker run <image>            # Lance un conteneur depuis une image
docker run -d <image>         # Lance un conteneur en arrière-plan (détaché)
docker run --rm <image>       # Supprime le conteneur après son arrêt
docker run -it <image> bash   # Lance un conteneur en mode interactif avec un shell
docker stop <id>              # Stoppe un conteneur
docker start <id>             # Démarre un conteneur arrêté
docker restart <id>           # Redémarre un conteneur
docker rm <id>                # Supprime un conteneur arrêté
docker logs <id>              # Affiche les logs d’un conteneur
docker logs -f <id>           # Affiche les logs en temps réel
docker exec -it <id> bash     # Ouvre un shell interactif dans un conteneur
docker inspect <id>           # Affiche les détails d’un conteneur
```

## 🖼 Gestion des Images
```sh
docker images                 # Liste des images locales
docker pull <image>           # Télécharge une image depuis Docker Hub
docker build -t <nom>:<tag> . # Construit une image à partir d’un Dockerfile
docker rmi <image>            # Supprime une image locale
docker tag <image> <repo>:<tag>  # Ajoute un tag à une image
docker push <repo>:<tag>      # Envoie une image sur un registre distant
```

## 📦 Volumes et Réseaux
```sh
docker volume ls              # Liste les volumes
docker volume create <nom>    # Crée un volume
docker volume rm <nom>        # Supprime un volume
docker network ls             # Liste les réseaux
docker network create <nom>   # Crée un réseau personnalisé
docker network inspect <nom>  # Détails sur un réseau
docker network rm <nom>       # Supprime un réseau
```

## 🔍 Autres commandes utiles
```sh
docker system prune           # Nettoie les ressources inutilisées (conteneurs, images, volumes)
docker stats                  # Affiche l’utilisation des ressources des conteneurs
docker top <id>               # Affiche les processus en cours dans un conteneur
docker cp <id>:<chemin> <dest>  # Copie un fichier depuis un conteneur
docker info                   # Affiche les informations système Docker
```

## 🛠 Commandes Docker Compose
### 🚀 Démarrage et gestion des services
```sh
docker-compose up             # Démarre tous les services définis dans docker-compose.yml
docker-compose up -d          # Démarre les services en mode détaché (en arrière-plan)
docker-compose down           # Stoppe et supprime les conteneurs, réseaux et volumes associés
docker-compose restart        # Redémarre tous les services
docker-compose stop           # Stoppe tous les services
docker-compose start          # Démarre les services arrêtés
```

### 📜 Logs et Debug
```sh
docker-compose logs           # Affiche les logs de tous les services
docker-compose logs -f        # Affiche les logs en temps réel
docker-compose ps             # Liste les conteneurs en cours
```

### 🔧 Exécution et Maintenance
```sh
docker-compose exec <service> bash  # Ouvre un shell dans un service en cours d’exécution
docker-compose build                # Construit ou reconstruit les images des services
docker-compose pull                 # Télécharge les dernières images depuis Docker Hub
docker-compose config               # Valide et affiche la configuration du fichier `docker-compose.yml`
```

## 🗑 Commandes de Nettoyage Docker

### 🚀 Supprimer tous les conteneurs
```sh
docker rm -f $(docker ps -aq)
```

### 🖼 Supprimer toutes les images
```sh
docker rmi -f $(docker images -q)
```

### 📦 Supprimer tous les volumes
```sh
docker volume rm $(docker volume ls -q)
```

### 🔗 Supprimer tous les réseaux
```sh
docker network rm $(docker network ls -q)
```

### 🏗 Supprimer la liste des builds
```sh
docker builder prune -f
```

### 💣 Supprimer tout d'un coup (conteneurs, images, volumes et réseaux)
```sh
docker system prune -a --volumes -f
```

⚠ **Attention** : Ces commandes supprimeront toutes les ressources Docker, assurez-vous de ne rien perdre d’important avant de les exécuter !

