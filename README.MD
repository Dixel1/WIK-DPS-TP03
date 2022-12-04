#INSTRUCTIONS

##Build + démarrage du cluster (docker compose)
- Lancer la commande *docker compose up --build*
image.png
image.png
image.png

- Sur *http://localhost:8081/* on constate le bon fonctionnement de l'API avec un affichage vide en erreur 404.
image.png

- Sur *http://localhost:8081/ping* on constate le bon fonctionnement de l'API avec un affichage des headers de la requête.
image.png

    - Lors de la requête sur /PING, le terminal depuis lequel nous avons lancé le cluster affiche le serveur ayant répondu (fonctionnement par distribution Roundrobin) :
    image.png

- Afin d'arreter le cluster (docker compose), faire un *CTRL + C* dans le terminal ayant servi à lancer ce même cluster.
image.png