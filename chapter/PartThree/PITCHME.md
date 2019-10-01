@snap[text-08]
# Amélioration de la stack TICK
@snapend

+++
@snap[north span-100 text-05]
## Amélioration de TELEGRAF
@snapend

configuration du partage de fichier avec docker

@snap[west span-50]
aller dans virtualbox pour désigner un dossier @img[](assets/img/shareFolder.png)
@snapend

@snap[east span-50]
ouvrir un cmd ou powershell et exécuter la commande `docker-machine restart`
@snapend

+++
docker run telegraf telegraf config > telegraf.config

@box[]([[outputs.influxdb]]
    urls = ["http://influxdb:8086"])

docker run -d --rm --name telegraf --net=influxdb -v /Docker/telegraf.conf:/etc/telegraf/telegraf.conf:ro telegraf

+++
@snap[north span-100 text-05]
## Mise en place de Kapacitor
@snapend
@snap[west span-100]
docker pull kapacitor:latest
docker run -d --rm --name kapacitor --network=influxdb -p 9092:9092 kapacitor
docker run --rm kapacitor kapacitord config > kapacitor.conf
@snapend
