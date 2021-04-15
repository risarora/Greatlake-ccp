
## Week 1 - Learning Material - Compute, Organization & IAM (~ 3.5 Hours)

### Module 1 - Core Building Blocks, Abstraction, AWS Console (~20mins)
### Module 2 - Compute - Elastic Compute Cloud or EC2 (~1hr)
### Module 2a - AWS EC2 Step 3 - Advanced Features Part I (~25mins
### Module 2b - AWS EC2 Step 3 - Advanced Features Part II (~10 mins)

![image](https://user-images.githubusercontent.com/4485129/114829617-f0089580-9de8-11eb-96a4-fc1ae411f751.png)

### Module 3 - How to SSH in to an EC2 Instance (~15mins)

<details>
 The following options are available to login via SSH from a Windows machine

1. Using Putty [Recommended]
https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html
https://www.youtube.com/watch?v=bi7ow5NGC-U

2. Using the Windows Terminal App from the Windows Store
Only available on Windows 10 version 18362.0 or higher
https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab
Has direct support for SSH commands

3. Installing Linux on Windows 10
https://itsfoss.com/install-bash-on-windows/

4. Using GitBash terminal
http://guides.beanstalkapp.com/version-control/git-on-windows.html
https://www.youtube.com/watch?v=rWboGsc6CqI

5. Chrome Secure Shell App
This application is an alternative way to SSH to instances in the cloud.This is not an environment to run scripts in your local machine, a local terminal window will be required for that
https://chrome.google.com/webstore/detail/secure-shell-app/pnhechapfaindjhompbnflcldabbghjo?hl=en-GB
https://www.youtube.com/watch?v=nHVptUyHcyE

</details>

### Module 4 - Load Balancing, Fault Tolerance & CloudWatch(~1hr)
<details>
 
![image](https://user-images.githubusercontent.com/4485129/114665766-0cd69780-9d1b-11eb-9680-4a0aeafa9f70.png)

* Install Tomcat    

```
ubuntu@ip-172-31-57-61:~$ sudo apt install apache2
Reading package lists... Done
.....
ubuntu@ip-172-31-57-61:~$ 
```

* Server available   
![image](https://user-images.githubusercontent.com/4485129/114836523-62c93f00-9df0-11eb-9486-952196e07444.png)


* Update the index.html with server name
```
ubuntu@ip-172-31-57-61:~$ sudo su
root@ip-172-31-57-61:/home/ubuntu# cd /var/www/html
root@ip-172-31-57-61:/var/www/html# ls 
index.html
root@ip-172-31-57-61:/var/www/html# echo " Hello from Server 1 " > index.html 
root@ip-172-31-57-61:/var/www/html# cat index.html 
 Hello from Server 1 
root@ip-172-31-57-61:/var/www/html# echo "ok" > health.html
root@ip-172-31-57-61:/var/www/html# cat health.html
 ok
root@ip-172-31-57-61:/var/www/html# curl localhost
 Hello from Server 1 
root@ip-172-31-57-61:/var/www/html#

```

* Message from server 
![image](https://user-images.githubusercontent.com/4485129/114837054-ea16b280-9df0-11eb-9fb8-d145abac1610.png)

* Server health check      
![image](https://user-images.githubusercontent.com/4485129/114839930-edf80400-9df3-11eb-90b5-3b03a436a456.png)


* Stop the tomcat service
![image](https://user-images.githubusercontent.com/4485129/114831050-8be6d100-9dea-11eb-8990-e4cdf26f2d40.png)

### Create Load Balancer

![image](https://user-images.githubusercontent.com/4485129/114850836-cd817700-9dfe-11eb-9352-ebb3cdf88f30.png)

* associate Loab balancer with atleast two sub nets  
![image](https://user-images.githubusercontent.com/4485129/114853665-a7110b00-9e01-11eb-99ba-f28ead7439cb.png)

* Create Target Group 
![image](https://user-images.githubusercontent.com/4485129/114853273-3d90fc80-9e01-11eb-9631-3029301e30e3.png)

* Setup Health Check    
![image](https://user-images.githubusercontent.com/4485129/114853148-1fc39780-9e01-11eb-83a8-f71089680bf4.png)

* register Targets 
![image](https://user-images.githubusercontent.com/4485129/114853390-5c8f8e80-9e01-11eb-82a0-ccd096014fe7.png)



#### Create Target Group

![image](https://user-images.githubusercontent.com/4485129/114840374-6068e400-9df4-11eb-9a74-f881a2f9cf23.png)

![image](https://user-images.githubusercontent.com/4485129/114840444-71b1f080-9df4-11eb-8750-50a9a33ff8b6.png)

![image](https://user-images.githubusercontent.com/4485129/114840574-8f7f5580-9df4-11eb-8551-d2ecce6b48aa.png)

* Target Group not yet associated with a load balancer
![image](https://user-images.githubusercontent.com/4485129/114840757-bfc6f400-9df4-11eb-8f95-9bd2f0d55087.png)



#### Associate Load Balancer with Target Group

</details>

#### Load Balancer Additional Information

<details>
 
##### A. Network Load Balancer

A Network Load Balancer functions at the fourth layer of the Open Systems Interconnection (OSI) model. It can handle millions of requests per second. After the load balancer receives a connection request, it selects a target from the target group for the default rule. It attempts to open a TCP connection to the selected target on the port specified in the listener configuration.

When you enable an Availability Zone for the load balancer, Elastic Load Balancing creates a load balancer node in the Availability Zone. By default, each load balancer node distributes traffic across the registered targets in its Availability Zone only. If you enable cross-zone load balancing, each load balancer node distributes traffic across the registered targets in all enabled Availability Zones.

If you enable multiple Availability Zones for your load balancer and ensure that each target group has at least one target in each enabled Availability Zone, this increases the fault tolerance of your applications. For example, if one or more target groups does not have a healthy target in an Availability Zone, we remove the IP address for the corresponding subnet from DNS, but the load balancer nodes in the other Availability Zones are still available to route traffic. If a client doesn't honor the time-to-live (TTL) and sends requests to the IP address after it is removed from DNS, the requests fail.

For TCP traffic, the load balancer selects a target using a flow hash algorithm based on the protocol, source IP address, source port, destination IP address, destination port, and TCP sequence number. The TCP connections from a client have different source ports and sequence numbers, and can be routed to different targets. Each individual TCP connection is routed to a single target for the life of the connection.

NLB is a great option for use cases where the client needs to keep the TCP connection open for long periods of time. If we use this for web applications using http(s) then we will observe that all the requests for a given user (browser instance) will always connect to a single backend web/application server.

Read more about AWS NLB here.
https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html
 

##### B. Application Load Balancer

Recently, some additional features of the load balancer have been introduced. The summary of the ALB capabilities are as follows:

1. Weighted Target Groups for ALB - You can now use traffic weights for your ALB target groups; this will be very helpful for blue/green deployments, canary deployments, and hybrid migration/burst scenarios. You can register multiple target groups with any of the forward actions in your ALB routing rules, and associate a weight (0-999) with each one. For example, we can send 70% of the traffic to tg1 and the remaining 30% to tg2.

2. Least Outstanding Requests for ALB - You can now balance requests across targets based on the target with the lowest number of outstanding requests.

You can read the very short blog here.
https://aws.amazon.com/blogs/aws/aws-load-balancer-update-lots-of-new-features-for-you/

</details>

### Module 5 - Windows EC2 Instance, Instance Pricing (~ 15mins)
### Module 6 - Identity & Access Management (~15mins)

### References 

1. https://tutorialsdojo.com/aws-cheat-sheet-aws-elastic-load-balancing-elb/
2. https://tutorialsdojo.com/aws-cheat-sheet-aws-elastic-load-balancing-elb/
