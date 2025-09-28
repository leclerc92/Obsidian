---
MOC: "[[DEVOBS]]"
---


---
***Références :***

---

## 📦 Gestion des Images

### Télécharger et gérer les images

```bash
# Télécharger une image depuis Docker Hub
docker pull <image_name>:<tag>

# Lister toutes les images locales
docker images
docker image ls

# Supprimer une image
docker rmi <image_id>
docker image rm <image_name>

# Supprimer toutes les images non utilisées
docker image prune
docker image prune -a  # Supprimer toutes les images non référencées

# Construire une image depuis un Dockerfile
docker build -t <image_name>:<tag> .
docker build -t <image_name>:<tag> <path_to_dockerfile>

# Afficher l'historique d'une image
docker history <image_name>

# Inspecter une image (métadonnées détaillées)
docker inspect <image_name>
```

## 🚀 Gestion des Conteneurs

### Créer et démarrer des conteneurs

```bash
# Créer et démarrer un conteneur
docker run <image_name>
docker run -d <image_name>  # En arrière-plan (détaché)
docker run -it <image_name> /bin/bash  # Mode interactif avec terminal

# Créer un conteneur avec des options courantes
docker run -d --name <container_name> -p <host_port>:<container_port> <image_name>

# Créer un conteneur avec montage de volume
docker run -d -v <host_path>:<container_path> <image_name>
docker run -d -v <volume_name>:<container_path> <image_name>

# Créer un conteneur avec variables d'environnement
docker run -d -e <VAR_NAME>=<value> <image_name>
```

### Gérer les conteneurs existants

```bash
# Lister les conteneurs en cours d'exécution
docker ps
docker container ls

# Lister tous les conteneurs (y compris arrêtés)
docker ps -a
docker container ls -a

# Démarrer/arrêter/redémarrer un conteneur
docker start <container_id_or_name>
docker stop <container_id_or_name>
docker restart <container_id_or_name>

# Tuer un conteneur (arrêt forcé)
docker kill <container_id_or_name>

# Supprimer un conteneur
docker rm <container_id_or_name>
docker rm -f <container_id_or_name>  # Force la suppression

# Supprimer tous les conteneurs arrêtés
docker container prune
```

### Interagir avec les conteneurs

```bash
# Exécuter une commande dans un conteneur en cours
docker exec <container_id_or_name> <command>
docker exec -it <container_id_or_name> /bin/bash  # Terminal interactif

# Attacher le terminal à un conteneur en cours
docker attach <container_id_or_name>

# Copier des fichiers entre hôte et conteneur
docker cp <host_path> <container_id>:<container_path>
docker cp <container_id>:<container_path> <host_path>

# Afficher les logs d'un conteneur
docker logs <container_id_or_name>
docker logs -f <container_id_or_name>  # Suivi en temps réel
docker logs --tail 50 <container_id_or_name>  # 50 dernières lignes

# Afficher les statistiques d'utilisation
docker stats <container_id_or_name>
docker stats  # Tous les conteneurs en cours

# Inspecter un conteneur
docker inspect <container_id_or_name>
```

## 🔗 Gestion des Réseaux

```bash
# Lister les réseaux
docker network ls

# Créer un réseau
docker network create <network_name>
docker network create --driver bridge <network_name>

# Connecter un conteneur à un réseau
docker network connect <network_name> <container_name>

# Déconnecter un conteneur d'un réseau
docker network disconnect <network_name> <container_name>

# Inspecter un réseau
docker network inspect <network_name>

# Supprimer un réseau
docker network rm <network_name>

# Supprimer les réseaux non utilisés
docker network prune
```

## 💾 Gestion des Volumes

```bash
# Lister les volumes
docker volume ls

# Créer un volume
docker volume create <volume_name>

# Inspecter un volume
docker volume inspect <volume_name>

# Supprimer un volume
docker volume rm <volume_name>

# Supprimer les volumes non utilisés
docker volume prune

# Monter un volume lors du run
docker run -v <volume_name>:<container_path> <image_name>
docker run -v <host_path>:<container_path> <image_name>  # Bind mount
```

## 🐙 Docker Compose

```bash
# Démarrer les services définis dans docker-compose.yml
docker-compose up
docker-compose up -d  # En arrière-plan

# Démarrer des services spécifiques
docker-compose up <service_name>

# Construire les images avant de démarrer
docker-compose up --build

# Arrêter les services
docker-compose down
docker-compose down -v  # Supprime aussi les volumes

# Voir les logs
docker-compose logs
docker-compose logs <service_name>
docker-compose logs -f  # Suivi en temps réel

# Lister les services en cours
docker-compose ps

# Exécuter une commande dans un service
docker-compose exec <service_name> <command>

# Redémarrer les services
docker-compose restart
docker-compose restart <service_name>
```

*exemple de fichier docker-compose.yml :*

```yml
version: '3.8'
services:
  rstudio:
    image: rocker/tidyverse:latest
    container_name: rstudio-dev
    ports:
      - "8787:8787"
    environment:
      - PASSWORD=rstudio123
      - USERID=1000
      - GROUPID=1000
    volumes:
      - ~/Documents/R-projects:/home/rstudio/projects
      - ~/Documents/R-library:/usr/local/lib/R/site-library
      - ~/Documents/R-data:/home/rstudio/data
    restart: unless-stopped
```
## 🧹 Nettoyage et Maintenance

```bash
# Nettoyer tout ce qui n'est pas utilisé
docker system prune
docker system prune -a  # Plus agressif

# Nettoyer par type de ressource
docker container prune  # Conteneurs arrêtés
docker image prune      # Images non utilisées
docker volume prune     # Volumes non utilisés
docker network prune    # Réseaux non utilisés

# Afficher l'utilisation de l'espace disque
docker system df

# Afficher des informations système détaillées
docker system info
```

## 🔍 Debugging et Inspection

```bash
# Afficher les processus dans un conteneur
docker top <container_id_or_name>

# Afficher les changements de fichiers dans un conteneur
docker diff <container_id_or_name>

# Exporter un conteneur vers une archive tar
docker export <container_id_or_name> > container.tar

# Importer une archive tar comme image
docker import container.tar <image_name>:<tag>

# Sauvegarder une image vers une archive tar
docker save <image_name> > image.tar

# Charger une image depuis une archive tar
docker load < image.tar
```

## 🏷️ Tags et Registry

```bash
# Créer un tag pour une image
docker tag <source_image> <target_image>:<tag>

# Pousser une image vers un registry
docker push <image_name>:<tag>

# Se connecter à un registry
docker login <registry_url>
docker login  # Docker Hub

# Se déconnecter
docker logout
```

## ⚙️ Options Courantes

### Principales options pour `docker run`

```bash
-d, --detach          # Exécuter en arrière-plan
-it                   # Mode interactif avec TTY
--name <name>         # Nommer le conteneur
-p <host>:<container> # Mapper les ports
-v <host>:<container> # Monter un volume
-e <VAR>=<value>      # Variable d'environnement
--rm                  # Supprimer automatiquement à l'arrêt
--restart <policy>    # Politique de redémarrage (no|always|on-failure|unless-stopped)
--network <network>   # Connecter à un réseau spécifique
--memory <limit>      # Limiter la mémoire (ex: 512m, 2g)
--cpus <number>       # Limiter les CPU (ex: 1.5)
```

## 📋 Exemples Pratiques

```bash
# Démarrer une base de données MySQL
docker run -d --name mysql-db -e MYSQL_ROOT_PASSWORD=secret -p 3306:3306 mysql:8.0

# Démarrer un serveur web nginx avec un volume
docker run -d --name web-server -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx

# Démarrer Redis avec persistance
docker run -d --name redis-server -v redis-data:/data -p 6379:6379 redis:alpine

# Construire et démarrer avec Docker Compose
docker-compose up --build -d

# Exécuter des commandes de maintenance
docker exec -it mysql-db mysql -u root -p
docker exec -it web-server /bin/bash
```


```shell
docker run -d \
  --name rstudio-container \
  -p 8787:8787 \
  -e PASSWORD=rstudio123 \
  -v ~/Documents/R-projects:/home/rstudio/projects \
  rocker/tidyverse:latest
  ```
  
