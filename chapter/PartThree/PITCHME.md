# Amélioration de la stack TICK
+++
## Amélioration de TELEGRAF
+++
@snap[north span-100]
configuration du partage de fichier avec docker
@snapend

@snap[west span-100]
@ol
- aller dans virtualbox pour désigner un dossier @img[](assets/img/shareFolder.png)
- ouvrir un cmd ou powershell et exécuter la commande `docker-machine restart`
@olend
@snapend

@snap[east span-100]
docker run telegraf telegraf config > telegraf.config
@snapend

+++
## Mise en place de Kapacitor
+++
@snap[west span-100]
docker pull kapacitor:latest
docker run -d --rm --name kapacitor --network=influxdb -p 9092:9092 kapacitor
docker run --rm kapacitor kapacitord config > kapacitor.conf
@snapend
