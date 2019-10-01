@snap[text-08]
# Amélioration de la stack TICK
@snapend

+++
@snap[north span-100 text-05]
## Amélioration de TELEGRAF
### configuration du partage de fichier avec docker
@snapend

@snap[west span-50]
aller dans virtualbox pour désigner un dossier 
@snapend

@snap[east span-50]
@img[span-100](assets/img/shareFolder.png)
@snapend

@snap[south span-100 text-06]
ouvrir un cmd ou powershell
exécuter la commande `docker-machine restart`
@css[text-orange](Cette commande stoppera tous les containers actifs)
@snapend

+++?color=white
@snap[west span-200]
docker run telegraf telegraf config > telegraf.config

```
[[outputs.influxdb]]
    urls = ["http://influxdb:8086"]
```

docker run -d --rm --name telegraf --net=influxdb -v /Docker/telegraf.conf:/etc/telegraf/telegraf.conf:ro telegraf
@snapend
+++
@snap[north span-100 text-05]
## Mise en place de Kapacitor
@snapend
@snap[west span-50]
docker pull kapacitor:latest
docker run -d --rm --name kapacitor --network=influxdb -p 9092:9092 kapacitor
docker run --rm kapacitor kapacitord config > kapacitor.conf
@snapend
@snap[east span-50]
@css[text-04](Il faut modifier l'url par `http://kapacitor:9092/`)
@img[span-60](assets/img/kapacitor_config.png)
@snapend
