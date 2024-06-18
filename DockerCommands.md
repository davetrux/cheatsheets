# Docker Commands

## List Running Containers

```
docker ps
```

## List Running and Stopped Containers

```
docker ps -a
```

## Look at Container Log

```
docker logs <containerId>
```

## Shell Into A Container

Note: the container must have a shell. Alpine images do not have one for instance.

```
sudo docker exec -it <containerId> bash
```

## Find Orphaned Images
```
docker rmi $(docker images -q --filter "dangling=true")
```

## Remove Orphaned Volumes

```
docker volume ls -qf dangling=true
docker volume rm `docker volume ls -q -f dangling=true`
```

## Resource Usage

```
docker ps -q | xargs  docker stats --no-stream
```

## Copy Files

```
docker cp <instance-name>:<path> <localpath>
docker cp <localpath> <instance-name>:<path>
```

## Copy files from Stopped Container
```
docker cp <instance-name>:<path> <localpath> -
```

## Stop All Containers

```
sudo docker stop $(sudo docker ps -a -q)
```

## Remove All Containers

```
sudo docker rm $(sudo docker ps -a -q)
```

## Remove All Images

```
sudo docker rmi $(sudo docker images -q)
```


## Remove Containers for an Image

```
sudo docker rm $(sudo docker ps -a -q -f 'name=<containername>')
```

## Clear build cache

```
docker buildx prune -f
```

