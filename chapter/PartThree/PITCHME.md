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

@snap[west span-50]
@img[span-50](assets/img/shareFolder.png)
@snapend

+++
ouvrir un cmd ou powershell
exécuter la commande `docker-machine restart`
@snap[south span-100]
@box[bg-red text-white rounded box-padding](Il faudra redémarrer les containers suite à cette command `docker start container_name`)
@snapend

+++?color=white
docker run telegraf telegraf config > telegraf.config

```
[[outputs.influxdb]]
    urls = ["http://influxdb:8086"]
```

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
