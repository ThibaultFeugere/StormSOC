# Installation de Telegraf

Telegraf est un agent serveur piloté par plug-in pour collecter et rapporter des métriques, un seul agent est nécessaire par machine. 

Cet agent sait récupérer des métriques exposées au format Prometheus et propose 2 modes de récupération des métriques, via : 

- push : la métrique est poussée dans Telegraf par le composant qui l’expose 
- pull : Telegraf récupère la métrique en interrogeant le composant qui l’expose

## Installer Telegraf après Influxdb

Toujours dans le but de mettre en place la TIG Stack (Telegraf, Influxdb et Grafana), il est cohérent d'installer Telegraf après Influxdb afin de ne pas collecter des données dans le vide. Maintenant que Influxdb est monté, aucune donnée ne sera perdue.

## Installation de Telegraf sur Ubuntu 19.10


1. `sudo apt-get update && sudo apt-get install apt-transport-https`

On met à jour la liste et on install `apt-transport-https` pour accéder aux paquets en *https*.

2. `sudo apt-get install telegraf`

On installe Telegraf.

3. `sudo systemctl start telegraf`

On démarre Telegraf.

4. `sudo systemctl enable telegraf` 

On active le démarrage de Telegraf au démarrage de l'ordinateur.

Le fichier de configuration de Telegraf est `/etc/telegraf/telegraf.conf`. 
