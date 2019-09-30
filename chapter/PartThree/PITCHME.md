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
@img[](asset/img/shareFolder.png)
- ouvrir un cmd ou powershell et exécuter la commande
 `docker-machine restart`
@olend
@snapend

+++
## Mise en place de Kapacitor
+++
@snap[west span-100]
docker pull kapacitor:latest
docker run -d --name kapacitor --network:influxdb kapacitor
@snapend
