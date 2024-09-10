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
`Docker Volumes`: để lưu trữ dữ liệu cho việc sử dụng và tạo apps.

```shell
# create volume
docker volume create mysql-data ## Tạo một volume
docker volume rm my_volume ## Xóa một volume
docker volume inspect my_volume ## Hiển thị thông tin chi tiết về volume.



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

### 2.1 List running containers:-
```shell
docker container ls
docker container ls -a

docker ps # Liệt kê các container đang chạy.
docker ps -a # Liệt kê tất cả các container (bao gồm cả những container đã dừng lại)
docker ps -a -f status=running
```


```shell
docker run -d --name my_container nginx # Tạo và khởi động một container

docker stop my_container
docker start my_container
docker restart my_container


```
### 2.2 List only stopped containers:-
```shell
docker ps --filter "status=exited"
docker ps -f "status=exited"
```

```shell

docker ps -aq --no-trunc
docker container ps
docker container list

docker exec -it my_container bash # Thực thi một lệnh trong container đang chạy.


docker attach my_container //Đi vào một container đang chạy.
docker logs my_container //Xem logs của container.
```
2.3 Mounting a Host Directory in a Docker Container:
```shell
docker run -v /path/to/host/directory:/path/in/container my_image

docker run \
  -it \
  --platform linux/amd64 \
  --mount type=bind,src=.,dst=/usr/app \
  --mount type=volume,dst=/usr/app/node_modules \
  alpine:latest
```
- [how-to-mount-current-working-directory-to-your-docker-container](https://ritviknag.com/tech-tips/how-to-mount-current-working-directory-to-your-docker-container/)
- [docker-mount-host-filesystem](https://www.baeldung.com/linux/docker-mount-host-filesystem)
- [docker-mount-volume-guide-how-to-mount-a-local-directory](https://www.freecodecamp.org/news/docker-mount-volume-guide-how-to-mount-a-local-directory/)

## stack
```shell
docker stack ls
```

## service
`Docker Services`: hiểu đơn giản là gồm các conntainer của ứng dụng và mỗi service chạy 1 image đã được định nghĩa.
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

Docker Client: là cách mà bạn tương tác với docker thông qua command.
Docker Daemon: lắng nghe các yêu cầu từ Docker Engine thông qua giao thức HTTP hoặc Unix socket và thực hiện yêu cầu.
Docker Registry: nơi lưu trữ riêng của Docker Images. Images được push vào registry và client sẽ pull images từ registry.
Docker Hub: là một dịch vụ đám mây cho phép lưu trữ và chia sẻ các container Docker.
Docker Repository: là tập hợp các Docker Images cùng tên nhưng khác tag.
Docker Networking: là tính năng cho phép các container Docker tương tác và giao tiếp với nhau và với mạng bên ngoài một cách linh hoạt.
Docker Compose: Là công cụ để quản lý và triển khai nhiều ứng dụng (docker container) một cách dễ dàng.
Docker Swarm: để phối hợp triển khai container.


## Dockerizing a PHP
- [semaphoreci.com](https://semaphoreci.com/community/tutorials/dockerizing-a-php-application)
- [cloudways.com](https://www.cloudways.com/blog/docker-php-application/)