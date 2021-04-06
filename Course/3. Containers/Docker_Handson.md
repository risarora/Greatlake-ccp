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
