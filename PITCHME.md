# Coding4Fun
## A propos de la stack TICK
---
@span{north span-100}
# Objectif
@spanend

![intro](assets/img/intro.png)

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
@span[north span-100]
## Recupération d'une image influxdb
@spanend

@span[midpoint span-100]
@box[Pull influxdb](
    docker pull influxdb:lastest
    docker run -d -rm --name influxdb -p 8080:8080 - p8086:8086 influxdb
)
@spanend
+++
## Recupération d'une image telegraf

+++
## Recupération d'une image Chronograf

---
# Amélioration de la stack TICK
+++
## Amélioration de TELEGRAF
+++
@snap[north span-100]
configuration du partage de fichier avec docker
@ol
- aller dans virtualbox pour désigner un dossier
- ouvrir un cmd ou powershell et exécuter la commande 
@olend
```
docker-machine restart
```
@snapend
+++
## Mise en place de Kapacitor

---
# Allez plus loin
