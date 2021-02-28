# Managed Services on AWS

## Week 1 - Learning Material - Docker (~ 2 Hours)
<details>
  <summary>Click to expand!</summary>
 
### Module 1 - Course Background(~20 mins)
### Module 2 - Virtual Machines vs Containers (Docker)(~20 mins)
### Module 3 - The Container (Docker) Ecosystem(~30 mins)
### Module 4 - Docker - Hands On(~1hr)
#### Overlay2 Storage Driver for Docker
<details>
  <summary>Click to expand!</summary>
 As of Ubuntu 14.10, the aufs storage driver used by Docker has been deprecated and now the preferred storage driver for Linux distributions is overlay2.  As a result of this change, the location of the layers has been moved from
/var/lib/docker/aufs/layer 

to
/var/lib/docker/overlay2

Going forward, overlay2 is the default storage driver on Docker installations on Linux. If aufs must be used, it has to be explicitly configured.


Please follow the link below to learn more on this

https://docs.docker.com/storage/storagedriver/select-storage-driver/

These updates and changes do not impact the core operations of Docker.
</details>

</details>

## Week 2 - Learning Material - Elastic Container Services (~ 2 Hours)
<details>
  <summary>Click to expand!</summary>
 
### Module 5 - Deploying a Java Web App using Docker Containers(~1hr)
### Module 6 - Amazon Elastic Container Services(~15 mins)
### Module 7 - Amazon ECS & Docker - Hands On(~1hr)

</details>


## Additional - Landscape of Kubernetes (~2hr 15mins)
