# DOCKER MASTERY

Docker mastery couse

## Setup and install instructions

Tips and commands to install and setup a new machine

### Linux docker CE

Preferable way to setup a machine to run docker is through installation scripts

always go to https://get.docker.com/ 

to get script 

```
curl -fsSL https://get.docker.com -o get-docker.sh

sh get-docker.sh

```

### after installation - user access linux

give admin permission to the user to access docker engine socket

```
sudo -aG docker username

```


## Getting started commands

Check docker version and info

command line structure:
docker <command> <sub-command> (options)

### version

```
docker version
```
### info

```
docker info
```
### images

```
docker images 
```

## docker container 

command to manage containers must be used along with subcommands and options

### list containers running 

```
docker container ps
```
### list all containers including stopped
```
docker container ls -a
```
### run containers

starts a new container from an image

```
docker container run hello-world

```

### --name 

specifies a chosen name to the container to be run

```
docker container run --detach --name webhost --publish 8888:80 nginx

```

### --publish

publish a nginx image and exposes a port to the host machine

--publish binds left_port (on host) : to the right_port (container) 
    
Ex: publish 8888:80 
Result:
localhost:8888 : container:80

```
docker container run --detach --name webhost --publish 8888:80 nginx

```

### --detach

detaches the container to run in the background, and returns you to the shell prompt

```
docker container run --detach --name webhost --publish 8888:80 nginx

```

### --tty

allocate a pseudo-tty (terminal)

```
docker container run --tty

```

### --interactive

keep session open to receive terminal input


```
docker container run --interactive 

```

### -ti

combines --tty with --interactive when running a new container

ps: command changes the initial command to be run in the container so after exiting the container, it will stop running  

```
docker container run -ti nginx bash

```


### -ai

combines --attach command with --interactive when starting an existing container

```
docker container run -ai mycontainer 

```


### exec commands on running containers

combines --tty command with --interactive in an already running container

ps: exec creates an additional command on the container so after exiting the container it will 
still be up and running

```
docker exec -it mycontainer bash

```

### docker container stop

stops the container but doen't remove it from local images

```
docker container stop container_id_or_name
```

### docker container logs

list logs for a container

```
docker container logs container_id_or_name
```

### docker container top

list process running in a container

```
docker container top container_id_or_name
```

### docker container rm

removes a container from local 

```
docker container rm container_id_or_name
```

### docker container inspect

show metadata about the container (startup, config, volumes, networking, etc) 

```
docker container inspect container_id_or_name
```
### docker container stats

show live performance data for all containers or specific ones 

```
docker container stats
```


### docker container stats

show live performance data for all containers or specific ones 

```
docker container stats
```

