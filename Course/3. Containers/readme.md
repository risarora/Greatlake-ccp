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

#### Create docker container
```
docker pull tomcat:jre8

$ docker pull tomcat:jre8
jre8: Pulling from library/tomcat
c5e155d5a1d1: Pull complete 
221d80d00ae9: Pull complete 
4250b3117dca: Pull complete 
d1370422ab93: Pull complete 
deb6b03222ca: Pull complete 
9cdea8d70cc3: Pull complete 
968505be14db: Pull complete 
04b5c270ac81: Pull complete 
301d76fcab1f: Pull complete 
57ca7a0b9e79: Pull complete 
3c1d6826d7a3: Pull complete 
Digest: sha256:7cdf9dca1472da80e7384403c57b0632753a3a5cdf4f310fc39462e08af8ef39
Status: Downloaded newer image for tomcat:jre8
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
tomcat              jre8                3639174793ba        23 months ago       463MB
$ docker run -d -p 80:8080 tomcat:jre8
d34a7c5f24de72739085e4b46a400efc12c79abf0997422982fc26bf0b8a3a5b
$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS                  NAMES
d34a7c5f24de        tomcat:jre8         "catalina.sh run"   6 seconds ago       Up 9 seconds        0.0.0.0:80->8080/tcp   agitated_snyder
$ bash                      
bash-3.2$ ps -ef | grep [dD]ocker
    0    90     1   0 11:28AM ??         0:00.01 /Library/PrivilegedHelperTools/com.docker.vmnetd
1400276427  1091     1   0 11:29AM ??         0:04.60 /Applications/Docker.app/Contents/MacOS/Docker
1400276427  1154  1091   0 11:29AM ??         0:00.30 /Applications/Docker.app/Contents/MacOS/com.docker.osx.hyperkit.linux -watchdog fd:0 -max-restarts 5 -restart-seconds 30
1400276427  1159  1154   0 11:29AM ??         0:49.22 com.docker.db --url fd://3 --git /Users/rarora17/Library/Containers/com.docker.docker/Data/database
1400276427  1162  1154   0 11:29AM ??         0:00.07 com.docker.osxfs serve --address fd:3 --connect /Users/rarora17/Library/Containers/com.docker.docker/Data/connect --control fd:4
1400276427  1169  1154   0 11:29AM ??         0:13.63 com.docker.vpnkit --db /Users/rarora17/Library/Containers/com.docker.docker/Data/s40 --branch state --ethernet fd:3 --port fd:4 --introspection fd:5 --diagnostics fd:6 --vsock-path /Users/rarora17/Library/Containers/com.docker.docker/Data/connect --host-names docker.for.mac.localhost --listen-backlog 32
1400276427  1170  1154   0 11:29AM ??         0:06.17 com.docker.driver.amd64-linux -addr fd:3 -debug
1400276427  1196  1170   0 11:29AM ??         9:42.55 com.docker.hyperkit -A -m 2048M -c 6 -u -s 0:0,hostbridge -s 31,lpc -s 2:0,virtio-vpnkit,uuid=53982f00-fdfc-430c-b504-4d70c38c178d,path=/Users/rarora17/Library/Containers/com.docker.docker/Data/s50,macfile=/Users/rarora17/Library/Containers/com.docker.docker/Data/com.docker.driver.amd64-linux/mac.0 -s 3,ahci-hd,file:///Users/rarora17/Library/Containers/com.docker.docker/Data/com.docker.driver.amd64-linux/Docker.qcow2?sync=os&buffered=1,format=qcow,qcow-config=discard=true;compact_after_unmaps=262144;keep_erased=262144;runtime_asserts=false -s 4,virtio-9p,path=/Users/rarora17/Library/Containers/com.docker.docker/Data/s40,tag=db -s 5,virtio-rnd -s 6,virtio-9p,path=/Users/rarora17/Library/Containers/com.docker.docker/Data/s51,tag=port -s 7,virtio-sock,guest_cid=3,path=/Users/rarora17/Library/Containers/com.docker.docker/Data,guest_forwards=2376;1525 -l com1,autopty=/Users/rarora17/Library/Containers/com.docker.docker/Data/com.docker.driver.amd64-linux/tty,log=/Users/rarora17/Library/Containers/com.docker.docker/Data/com.docker.driver.amd64-linux/console-ring -f kexec,/Applications/Docker.app/Contents/Resources/moby/vmlinuz64,/Applications/Docker.app/Contents/Resources/moby/initrd.img,earlyprintk=serial console=ttyS0 com.docker.driver="com.docker.driver.amd64-linux", com.docker.database="com.docker.driver.amd64-linux" ntp=gateway mobyplatform=mac vsyscall=emulate page_poison=1 panic=1 -F /Users/rarora17/Library/Containers/com.docker.docker/Data/com.docker.driver.amd64-linux/hypervisor.pid
bash-3.2$ docker ps -a

CONTAINER ID        IMAGE               COMMAND             CREATED              STATUS              PORTS                  NAMES
d34a7c5f24de        tomcat:jre8         "catalina.sh run"   About a minute ago   Up About a minute   0.0.0.0:80->8080/tcp   agitated_snyder
bash-3.2$ 

bash-3.2$ docker stop agitated_snyder
agitated_snyder

```

#### Run 2 docker container one for port 80 and the 8080
```
bash-3.2$ docker exec -it agitated_snyder bash 
Error response from daemon: Container d34a7c5f24de72739085e4b46a400efc12c79abf0997422982fc26bf0b8a3a5b is not running
bash-3.2$ docker start agitated_snyder
agitated_snyder
bash-3.2$ docker exec -it agitated_snyder bash 
root@d34a7c5f24de:/usr/local/tomcat# ls
BUILDING.txt	 LICENSE  README.md	 RUNNING.txt  conf     lib   native-jni-lib  webapps
CONTRIBUTING.md  NOTICE   RELEASE-NOTES  bin	      include  logs  temp	     work
root@d34a7c5f24de:/usr/local/tomcat# cd webapps/
root@d34a7c5f24de:/usr/local/tomcat/webapps# ls
ROOT  docs  examples  host-manager  manager
root@d34a7c5f24de:/usr/local/tomcat/webapps# ls -al
total 28
drwxr-xr-x  7 root root  4096 May  4  2019 .
drwxr-sr-x  1 root staff 4096 May 16  2019 ..
drwxr-xr-x  3 root root  4096 May 16  2019 ROOT
drwxr-xr-x 14 root root  4096 May 16  2019 docs
drwxr-xr-x  6 root root  4096 May 16  2019 examples
drwxr-xr-x  5 root root  4096 May 16  2019 host-manager
drwxr-xr-x  5 root root  4096 May 16  2019 manager
root@d34a7c5f24de:/usr/local/tomcat/webapps# cp Helloword.war .
cp: cannot stat 'Helloword.war': No such file or directory
root@d34a7c5f24de:/usr/local/tomcat/webapps# 

```




#### Commit docker container
```
docker run -p -d 80:8080 -v 

docker commit 
docker save <IMAGE ID> > dockerimage.tar
```


### Module 6 - Amazon Elastic Container Services(~15 mins)

* Load Balancer
* Target Group
* Amazon ECS Fargate
* Amazon ECR
* Auto Scaling Groups
* Capacity, Task and Fraud
* Vertical and Horizontal Scalability.


### Module 7 - Amazon ECS & Docker - Hands On(~1hr)

</details>


## Additional - Landscape of Kubernetes (~2hr 15mins)

## Notes

* [Containers.pdf](https://github.com/risarora/Greatlake-ccp/files/6274194/Containers.pdf)

## Practice Exercise

[PRACTICE_LAB_Container_Docker_Images_Containers_Scripts.pdf](https://github.com/risarora/Greatlake-ccp/files/6274222/PRACTICE_LAB_Container_Docker_Images_Containers_Scripts.pdf)
