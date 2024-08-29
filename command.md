# Docker document

### commands
```shell
docker login
docker info
docker inspect nginx


docker system prune 
docker volumes prune
```

## 1.`Dockerfile`
Docker can build images automatically by reading the instructions from a Dockerfile. A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. This page describes the commands you can use in a Dockerfile.

## 2. `.dockerignore`
You can use `.dockerignore` file to exclude files and directories from the build context. For more information,

## 3. `compose.yaml`

## 4. Volumes
```shell
# create volume
docker volume create mysql-data ## Tạo một volume

# run mysql container in the background
$ docker run --name mysql-db -v mysql-data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:latest

# stop mysql container
docker rm -f mysql-db

# remove volume
docker volume remove mysql-data



docker volume ls                  ## List danh sách volume
docker volume inspect my-volume   ## Hiển thị thông tin của Volume
ll /var/lib/docker/volumes        ## Kiểm tra volume được tạo ra

```

### 4.1 Bind mounts

## 2. Container

### List running containers:-
```shell
docker container ls
docker container ls -a
docker ps


docker ps -a
docker ps -a -f status=running
```
### List only stopped containers:-
```shell
docker ps --filter "status=exited"
docker ps -f "status=exited"
```

```shell

docker ps -aq --no-trunc
docker container ps
docker container list



```

## stack
```shell
docker stack ls
```

## service
```shell
docker service ls
```

## Image
```shell
docker image ls
docker run image_name:tag_name

docker rmi
docker image rm
docker image rmi
docker image remove

docker image pull nginx
docker image inspect nginx
```

### run  image as container
```shell
docker run -it apache_snapshot /bin/bash
```

## Hub

```shell
docker search ubuntu
docker pull ubuntu
```
