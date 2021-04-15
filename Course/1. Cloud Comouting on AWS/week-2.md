## Auto Scaling

* User Data
```
#!/bin/bash
apt update -y
apt install apache2 -y
service apache2 start
IP_ADDR=${curl http://169.254.169.254/latest/meta-data/public-ipv4}
echo "Auto scale instance "$IP_ADDR > /var/www/html/index.htm
echo "ok" > /var/www/html/health.htm
```
