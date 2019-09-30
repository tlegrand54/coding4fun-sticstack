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
docker pull influxdb:latest 
docker run -d --rm --name influxdb --network=influxdb -p 8083:8083 -p 8086:8086 influxdb
@snapend
+++
@snap[north span-100]
## Recupération d'une image telegraf
@snapend
@snap[west span-100]
docker pull telegraf:latest 
docker run -d --rm --net=container:influxdb telegraf
@snapend
+++
@snap[north span-100]
## Recupération d'une image Chronograf
@snapend
@snap[west span-100]
docker pull chronograf:latest 
docker run -d --rm --name chronograf --network=influxdb -p 8888:8888 chronograf --influxdb-url=http://influxdb:8086
@snapend
+++
@snap[north span-100]
## Configuration des redirections de port
@snapend
@snap[midpoint span-100]
@img[](assets/img/redirection.png)
@snapend