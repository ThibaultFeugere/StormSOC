# Installation de Grafana

Grafana est un logiciel libre sous licence Apache 2.0 qui permet la visualisation de données. Il permet de réaliser des tableaux de bord et des graphiques depuis plusieurs sources dont des bases de données temporelle avec Influxdb par exemple.

## Installer Grafana en dernier

Etant donné que Grafana permet de faire de la Data Viz (Visualisation de données), il est cohérent d'installer Grafana à la fin puisque avant, il n'y aurait soit aucune base de données soit aucune source de données collectés

## Installation de Grafana sur Ubuntu 19.10

1. `wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -`

On télécharge la clé GPG et on l'ajoute.

2. `sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"`

On ajoute le repository.

3. `sudo apt-get update && sudo apt-get install grafana`

On met à jour la liste et on installe Grafana.

4. `sudo systemctl start grafana-server`

On démarre Grafana.

5. `sudo systemctl enable grafana-server`

On active le démarrage de Grafana en même temps que l'ordinateur.

L'installation est terminée et la TIG Stack est prête. On peut accéder à Grafana via l'adresse http://127.0.0.1:3000.
