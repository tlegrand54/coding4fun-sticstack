@snap[north span-100 text-08]
# Annexe
@snapend

```
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
docker image rm $(docker image ls -a -q)
```
