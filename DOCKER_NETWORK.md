# DOCKER NETWORKS

Docker networks module.

Docker's default network is called 'bridge', this network is NAT'ed behind the Host IP

There are also two others networks: 

host: gains performance by skipping virtual network, but sacrifices security of container model, attach the container directly to the host interface.

none: removes eth0 and only leaves you with localhost interface in container


## Basic networks commands

### List networks 

```
docker network ls 

```
### Inspect network

inspec a network

```
docker network inspect 

```
### create a network

creates a new  network

```
docker network create --driver(optional) 

```

### attach a network

attaches a container to a network

```
docker network connect network_id container_id

```
### disconnect a network 

disconnects a network from container 

```
docker network disconnect network_id container_id

```

## DNS
Docker has a built in DNS server

ps: it is an anti-pattern to use static IP addresses in containers, the main reason is
container apps are designed to be replaced, modified, removed dynamically and containers shouldn't rely on ip'

### Hostnames

By default the container's hostname  is the same as its name, but an alias can be set

### DNS ALIAS

Alias is a great strategy when we want to create manually two instances of some container,
even though it's not a load balancer it can be useful

ex: runs a container and give it an alias; 'search'

```
docker container run -d --net my-network -d --net-alias search elasticsearch:2
```