# Rendu de projet Labo sécu 2020

## Diffusion du documents

### Membres du projet

- Steven Dias
- Thibault Feugere

### Liste des personnes autorisés à consulter ce document : 

- Steven Dias (Labo SSI)
- Thibault Feugère (Labo SSI)
- Louis Leveque (Labo SSI)
- Alexandre Tricaud (Labo SSI)

## Sommaire 

1. [Présentation du sujet SOC](##Présentation-du-sujet-SOC)
    1. [Le contexte](##Le-contexte)
    2. [Qu'est ce qu'un SOC](##Qu'est-ce-qu'un-SOC)
    3. [Problématique](##Problématique)
2. [Présentation de StormSOC](##Présentation-de-StormSOC)
    1. [Le Projet StormSOC](##Le-Projet-StormSOC)
    2. [Les choix technologiques](##Les-choix-technologiques)
    3. [Les problemes rencontrés](##Les-problemes-rencontrés)
3. [Présentation technique du projet](##Présentation-technique-du-projet)
    1. [Doc d'installation](##Doc-d'installation)
    2. [Etudes des différentes techniques de détéction](##Etudes-des-différentes-techniques-de-détéction)
    3. [Etudes des différentes techniques d'analyse de log](##Etudes-des-différentes-techniques-d'analyse-de-log)
4. [Conclusion](##Conclusion) 

## Présentation du sujet SOC

### Le contexte

De nos jours il y a de plus en plus de Systèmes d'informations qui voient le jour et les SI existant ne font que s'agrandir.
Cette expansion présente des risques et de plus en plus de cyberattaques voient le jour, les motivations sont nombreuses :

- Étatique, 
- Éthique, 
- Espionnage, 
- Rançonnage,
- Économique. 

Bref, la menace est de plus en plus grande et pour faire face à cette menace, il faut désormais se munir d'outils, et de mesure de sécurité pour se mettre à l'abri un minimum et pour permettre d'avoir une défense correcte face à un attaquant.

De ce fait, on a vu apparaître un mot qui revient trés souvent lorsque l'on parle de stratégie de défense : Le Security Operation Center associé à son anagramme SOC.

### Qu'est ce qu'un SOC

Un Security Operation Center dans un SI, désigne une division qui assure la sécurité du SI et de ses informations.

Un SOC est lié aux personnes, aux processus et aux technologies utilisées pour s’assurer de la connaissance de la situation grâce à la détection, au confinement et à l'assainissement des menaces informatiques.

Le SOC est une plateforme permettant la supervision et l’administration de la sécurité du système d'information au travers d’outils de collecte, de corrélation d'événements et d'interventions à distance. Le SIEM (Security Information Event Management) est l'outil principal du SOC puisqu'il permet de gérer les événements d'un SI.

L’objectif d’un SOC est de détecter, analyser et remédier aux incidents de cybersécurité à l’aide de solutions technologiques et d’un ensemble de démarches. 

Ils surveillent et analysent l'activité sur les réseaux, les serveurs, les terminaux, les bases de données, les applications, les sites Web et autres systèmes, à la recherche de signaux faibles ou de comportements anormaux qui pourraient être le signe d'un incident ou d'un compromis en matière de sécurité. 

Le SOC doit veiller à ce que les incidents de sécurité potentiels soient correctement identifiés, analysés, défendus, enquêtés et signalés.

Les SOC sont composés, en général, d’analystes et d’ingénieurs en sécurité, ainsi que de managers supervisant les opérations de sécurité. 
Les capacités supplémentaires de certains SOC peuvent inclure l'analyse avancée, la cryptanalyse et l'ingénierie inverse des logiciels malveillants pour analyser les incidents.

Les équipes SOC travaillent étroitement avec les équipes d’intervention afin de s’assurer que le problème de sécurité soit bien réglé une fois qu’il a été découvert.

### Problématiques 

De nos jours, le terme SOC est un terme qui fait référence à un salle avec plein d'écrans et plein de graphique en temps réel accompagnés de beaux graphiques, mais un SOC ne se résume pas à cela c'est un métier à part entière et c'est dans cette problématique que nous avons voulus tenter l'expérience de découvrir ce métier et les technologies qui l'entoure au sein de notre projet labo sécu 2020.

## Présentation du projet StormSOC

### Le Projet StormSOC

Dans le cadre du labo sécu 2020, nous avons décidé de monter une infrastructure SOC pour découvrir ce qu'est un SOC, démystifier le terme SOC qui est utilisé de manière abusive ces temps-ci et de découvrir le métier d'un analyste SOC.

## Présentation technique du projet

### Doc d'installation

#### Installation de la TIG Stack

Un SOC doit être visuel et l'outil de Data Viz Grafana nous a attiré. Nous sommes parti sur la Stack TIG qui est :

- Telegraf (open source)
- Influxdb (open source)
- Grafana (open source)

Cette Stack permet de monitorer une infrastructure.

Vous pouvez trouver les procédés pour la mise en place de chaque outil :

- [Installation de Influxdb](https://gitlab.com/thibaultfeugere/StormSOC/-/blob/master/installations/influxdb.md)
- [Installation de Telegraf](https://gitlab.com/thibaultfeugere/StormSOC/-/blob/master/installations/telegraf.md)
- [Installation de Grafana](https://gitlab.com/thibaultfeugere/StormSOC/-/blob/master/installations/grafana.md)

Avec du recule, l'ajout de Kapacitor aurait pu être intéressant. L'alternative à Grafana, Chronograf aurait pu être une piste à tester. Nous pensons qu'un SOC doit constamment être mis à jour et amélioré. Il est donc intéressant de savoir les pistes à explorer / explorable.
