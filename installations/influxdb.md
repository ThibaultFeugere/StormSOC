# Installation de Influxdb

InfluxDB est une *Time Series Database*, qui permet de compresser un large volume de données venant de multiples sources. InfluxDB vise à collecter le nombre croissant de données métriques. InfluxDB est écrite avec le langage de programmation GO (utilisé par Google).

## Installer Influxdb en premier

Pour notre SOC, nous avons choisi la *TIG Stack* (Telegraf, Influxdb et Grafana). Influxdb vient stocker le données, il est donc recommandé de l'installer en premier pour plusieurs raisons. Telegraf ne tournera pas dans le vide par la suite et Grafana aura des données à montrer seulement quand Telegraf et Influxdb seront installés.

## Installation

/!\ Avant de commencer, il faut s'assurer que les ports 8086 et 8088 ne sont pas occupés.

1. `curl -sL https://repos.influxdata.com/influxdb.key | sudo apt-key add -`
OK

2. `source /etc/lsb-release`

3. `echo "deb https://repos.influxdata.com/${DISTRIB_ID,,} ${DISTRIB_CODENAME} stable" | sudo tee /etc/apt/sources.list.d/influxdb.list`

On ajoute le repo à la liste et on rafraichît avec la commande update.

4. `sudo apt-get update && sudo apt-get install influxdb`

On télécharger Influxdb.

Influxdb est désormais installé mais celui-ci ne tourne pas encore, on peut le savoir en faisant la commande : `sudo systemctl status influxdb` et on voit : `inactive (dead)`

On peut alors démarrer Influxdb avec la commande : `sudo service influxdb start`

On aimerait bien que Influxdb se lance au démarrage de la machine, il suffit d'effectuer la commande : `sudo systemctl enable influxdb`

Désormais, Influxdb a le statut : `Active (running)` et démarre au démarrage.

La fichier de configuration est `/etc/influxdb/influxdb.conf`
