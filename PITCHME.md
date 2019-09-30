# Coding4Fun
## A propos de la stack TICK
---
@snap[north span-100]
# Objectif
@snapend

@img[](assets/img/intro.png)

---
# Presentation de la stack TICK
+++
## TELEGRAF
+++
## INFLUXDB
+++
## CHRONOGRAF
+++
## KAPACITOR

---
# Installation la stack TICK avec Docker
+++
@snap[north span-100]
## Création d'un réseau inter-container
@snapend
@snap[west span-100]
docker network create influxdb
@snapend
+++
@snap[north span-100]
## Recupération d'une image influxdb
@snapend
@snap[west span-100]
docker pull influxdb:lastest 
docker run -d -rm --name influxdb --network=influxdb -p 8083:8083 -p 8086:8086 influxdb
@snapend
+++
@snap[north span-100]
## Recupération d'une image telegraf
@snapend
@snap[west span-100]
docker pull telegraf:lastest 
docker run -d --name telegraf --network:influxdb -p 8080:8080 - p8086:8086 influxdb
@snapend
+++
@snap[north span-100]
## Recupération d'une image Chronograf
@snapend
@snap[west span-100]
docker pull influxdb:lastest 
docker run -d -rm --name influxdb -p 8080:8080 - p8086:8086 influxdb
@snapend
---
# Amélioration de la stack TICK
+++
## Amélioration de TELEGRAF
+++
@snap[north span-100]
configuration du partage de fichier avec docker
@snapend

@snap[west span-100]
@ol
- aller dans virtualbox pour désigner un dossier
- ouvrir un cmd ou powershell et exécuter la commande 
````
docker-machine restart
````
@olend
@snapend

+++
## Mise en place de Kapacitor

---
# Allez plus loin
