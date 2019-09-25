# Docker Commands, Help & Tips

### Show commands & management commands

```
$ docker
```

### Docker version info

```
$ docker version
```

### Show info like number of containers, etc

```
$ docker info
```

# WORKING WITH CONTAINERS

#### TIP: ABOUT Containers
- docker container run -d -p 80:80 --name nginx-server nginx
- Looked for image called nginx in image cache
- If not found in cache, it looks to the default image repo on Dockerhub
- Pulled it down (latest version), stored in the image cache
- Started it in a new container
- We specified to take port 80- on the host and forward to port 80 on the container
- We could do "$ docker container run --publish 8000:80 --detach nginx" to use port 8000
- We can specify versions like "nginx:1.09"
-Docker containers are often compared to virtual machines but they are actually just processes running on your host os. In Windows/Mac, 
-Docker runs in a mini-VM so to see the processes youll need to connect directly to that. On Linux however you can run "ps aux" and see the processes directly

### Create an run a container in foreground

```
$ docker container run -it -p 80:80 nginx
```

### Create an run a container in background

```
$ docker container run -d -p 80:80 nginx
```

### Create an run a container with environment variable

```
$ docker run -d -p 15002:80 --env ASPNETCORE_ENVIRONMENT=QA --name <containerName> <Imagename> .
```

### Shorthand

```
$ docker container run -d -p 80:80 nginx
```

### Naming Containers

```
$ docker container run -d -p 80:80 --name nginx-server nginx
```

### To get all the containers

```
$ docker container ls
```

### To remove a container

```
$ docker container rm <container id>
```

### Remove multiple containers

```
$ docker container rm [ID] [ID] [ID]
```

### Remove all containers

```
Use git bash
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
```

### Stop a container

```
$ docker stop <container id>
```

### Start a container

```
$ docker start <container id>
```

### Inspect a container

```
$ docker inspect <container id>
```

### SSH a container

```
$ docker exec –it <containerName> sh
```

### Pause a container

```
$ docker pause  <containerName>
```

### UnPause a container

```
$ docker unpause <containerName>
```

### Copy local file in to a container

```
$ docker container cp <fileName> <containerName>:/path
```

### Rename container name

```
$ docker rename container <containerName> <containerNewName>
```

### Download docker container files

```
$ docker cp <container name>:/src C:\Users\Kaushik\Desktop\DockerCodes
/src -->Working directory (Do docker inspect container id to find the working directory)
C:\Users\Kaushik\Desktop\DockerCodes-->Path where the container files needs to be copied
```

# WORKING with Images

#### TIP: ABOUT IMAGES

- Images are app bianaries and dependencies with meta data about the image data and how to run the image
- Images are no a complete OS. No kernel, kernel modules (drivers)
- Host provides the kernel, big difference between VM

### List the images we have pulled

```
$ docker image ls
```

### Build docker images from docker file

```
$ docker build -t <ImageName> .
```

### Tag docker images

```
$ docker tag <image name> <Image Name>:<Version>
```

### We can also just pull down images

```
$ docker pull <IMAGE>
```

### Remove image

```
$ docker rmi <IMAGEName>
```

### Remove multiple images

```
$ docker rmi <imageid1 imageid2>
```

### Remove all images

```
$ docker image prune --all
```

### Remove all images

```
$ docker tag <image name> <Image Name>:<Version>
```

### inspect image

```
$ docker inspect<image Id>
```

### save image as a tar file

```
$ docker save <imageName> -o tar File Name
```

### load image from your personal place

```
$ docker load -i tar <FileName>
```

# UI tool for docker

#### Tip:

-Use Kitematic tool to easily view docker containers running ,ports used and to pull a image


#Push docker image to docker hub

### To push Docker Image from Local System to Docker Hub	
```
Step 1)docker login 
Step 2)docker tag <Image Name> <su1991>/<Image Name>:<version>
Step 3)docker push <su1991>/<Image Name>:<version>
```
