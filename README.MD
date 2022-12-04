# INSTRUCTIONS

Toutes les instructions qui suivront doivent être effectuées depuis le dossier contenant le projet. Lors de l'ouverture du terminale vous pouvez vous deplécer avec en utilisant la commande *cd [...]*. Par exemple : 
![image](https://user-images.githubusercontent.com/63664894/205495826-bc1e7c13-b7e9-4f4b-8e49-1ee737c46166.png)

## Build + démarrage du cluster (docker compose)
- Lancer la commande *docker compose up --build*
![image](https://user-images.githubusercontent.com/63664894/205495337-5f55adf9-2848-4755-8c22-a4461ff433fa.png)
- Sur *http://localhost:8081/* on constate le bon fonctionnement de l'API avec un affichage vide en erreur 404.
![image](https://user-images.githubusercontent.com/63664894/205495374-d15c485c-5d9e-4231-a0dd-e23ab36da74a.png)

- Sur *http://localhost:8081/ping* on constate le bon fonctionnement de l'API avec un affichage des headers de la requête.
![image](https://user-images.githubusercontent.com/63664894/205495411-23f406c6-df06-48f5-bd33-45a731f42907.png)

    - Lors de la requête sur /PING, le terminal depuis lequel nous avons lancé le cluster affiche le nom du serveur ayant répondu à la requête (chaque itération de requête sur /PING affiera le nom du serveur ayant répondu dans le Terminal) :
    ![image](https://user-images.githubusercontent.com/63664894/205495457-69696bcd-56b9-4463-a73b-9f4357d90b7f.png)

- Afin d'arreter le cluster (docker compose), faire un *CTRL + C* dans le terminal ayant servi à lancer ce même cluster.
![image](https://user-images.githubusercontent.com/63664894/205495639-8ac44823-0c2c-40dd-819c-ad0b3e231da6.png)

## docker-compose.yaml
Un fichier *docker-compose.yaml* est un fichier de configuration pour Docker Compose. Il permet de déployer, combiner et configurer plusieurs conteneurs docker en même temps. La "règle" Docker est d’externaliser chaque processus à son propre conteneur Docker.
Voir le fichier *docker-compose.yaml* : https://github.com/Sarvagon/WIK-DPS-TP03/blob/main/docker-compose.yaml

## NGINX (nginx.conf)
NGINX est un utilitaire permettant de créer, configurer et déployer un serveur proxy de manière simple. Il est donc possible d'automatiser son déploiement depuis Docker en utilisant un fichier *docker-compose.yaml* et un fichier de configuration *nginx.conf*.

## Round-robin
Le round-robin est utilisé ici par le proxy NGINX afin de répartir la charge trafic de l'API lors de requètes sur /PING. Il s'agit donc d'une méthode utilisée pour effectuer de l'ordonnancement de la répartition de charge.

*NOTE : L'api est accessible directement depuis l'adresse du proxy NGINX (adresse "front") qui lui permettra ensuite de répartir la charge des requête sur les différents noeuds du cluster de serveurs web contenant l'API.*
