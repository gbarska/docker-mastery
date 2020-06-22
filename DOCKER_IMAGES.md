# DOCKER IMAGES

Docker images start from base layers and get improvements on each release,  

each new layer that is added to an image is commited to the hub, and has a hash if other images
rely on the same layers the consumers of that layers won't need to download the layer twice,
also when uploading new images the repeated layers won't be upload again

docker images are receives unique image ids and can be referenced by multiple tags like v1, v2, latest etc..

### images history

```
docker history nginx:latest 

```

### Inspect images

inspect an image, shows all metadata info

```
docker image inspect nginx

```
## docker images and Docker Hub

We can create a custom image and commit it to the Docker Hub repository


### image tagging

creates a pointer to a specific commit of some image

```
docker image tag latest myusername/myimage

```


### docker login
login to docker hub account and saves the auth details to the file: .docker/config.json

```
docker login 

```

### docker logout

```
docker logout

```

### pushing images to docker hub

in order to upload an image we must login to the docker hub and push the already created image with tag command

docker image push myusername/myimage
