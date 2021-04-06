* linux 
```
chmod 400 gl.pem
```

* Windows
```
$path = ".\gl.pem"
# Reset to remove explicit permissions
icacls.exe $path /reset
# Give current user explicit read-permission
icacls.exe $path /GRANT:R "$($env:USERNAME):(R)"
# Disable inheritance and remove inherited permissions
icacls.exe $path /inheritance:r
```

* Connect to server 

```
ssh -i "gl.pem" ubuntu@ec2-13-232-201-211.ap-south-1.compute.amazonaws.com
```

* Install docker
```
sudo apt install docker.io
```
* add user permissions
```
sudo usermod -aG docker ubuntu
```
* logout login

```
docker ps
```
```
ps -ef | grep [dD]ocker
```

* install busybox image
```
ubuntu@ip-172-31-11-141:~$ docker run --rm busybox:latest
Unable to find image 'busybox:latest' locally
latest: Pulling from library/busybox
8b3d7e226fab: Pull complete
Digest: sha256:ce2360d5189a033012fbad1635e037be86f23b65cfd676b436d0931af390a2ac
Status: Downloaded newer image for busybox:latest
ubuntu@ip-172-31-11-141:~$ 
ubuntu@ip-172-31-11-141:~$ docker run --rm busybox:latest /bin/echo "Hello world"
Hello world
ubuntu@ip-172-31-11-141:~$ 
```
