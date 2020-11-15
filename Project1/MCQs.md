# Answer the following questions

Q1	What is the default setting for DNS hostnames when a new VPC is created?
a) Enabled
b) Disabled
c) Can be set during VPC creation
d) Depends on the region used
Enter your answer here	Disabled		

Q2	What is the term used for the application server when we use it to log into the database server
a) Bastion Host
b) NAT Gateway
c) Tunnel Interface
d) SSH Gateway
Enter your answer here	Basion Host		

Q3	The database server security group in this exercise has to keep port 3306 open. Which protocol uses this port to communicate?
a) HTTPS
b) RDP
c) TCP
d) SCP
Enter your answer here	TCP		

Q4	Which port is being used by Mattermost to communicate with the client  application
a) 8080
b) 80
c) 443
d) 8065
Enter your answer here	443		

Q5	Which of the following is a reason why we cannot set the CIDR block for the public subnet to 10.0.2.0/16, assuming the values for the other CIDR blocks are the same as mentioned in the instructions?
a) CIDR block overlaps with existing block
b) CIDR block is not a valid CIDR
c) CIDR block does not fall within the VPC
d) There is no reason, this is a perfectly valid CIDR
Enter your answer here	a) CIDR block overlaps with existing block		

Q6	In this exercise, you have been asked tob create 3 EC2 instances - the application server, the database server and the NAT instance. Each of these instances have their own security groups with a set of ports to be kept open. One of those ports is entirely unnecessary for the given architecture to function. Which of the ports given in the option below is it? 
a) Port 22 on the NAT instances
b) Port 3306 on the database server
c) Port 443 on the NAT instance
d) Port 22 on the application server
Enter your answer here	a) Port 22 on the NAT instances		

Q7 	Describe the steps you would take to increase security of the servers you have deployed so that they are not reachable from external sources
 
1. Restrict Incoming Traffic
Restrict incoming traffic from desired ip's , ports and regions./

1. Restrict Outbound Rules
The Outbound ports should not be opened to all.

3. Unused Security Groups should be deleted.
All unused security groups should be deleted to prevent accidently assigning an unwanter group to a server.

4. Restrict Security Group Modifications
Use AWS Identity and IAM to manage user and group permissions. It enables users to control who can make provision/delete/modify any resources across AWS. To add further security checks, AWS IAM provides resource-level IAM controls for EC2 and RDS resources.

5. Enable Tracking and Alerting
Use service like AWS CloudTrail to track traffic to ec2 servers.

Q8	Descibe the steps required to deploy the given application in an autoscaling environment

Step 1: Create a launch template
In the Amazon EC2 Dashboard,  create a Launch Templates by specifying the below 
* Template Name, 
* AMI, 
* Instance type, and other details. 

Step 2: Create an Auto Scaling group
Using the Auto Scaling wizard, create an Auto Scaling group specifying a name, size, and network for the Auto Scaling group.

Step 3: Create an Elastic Load Balancers 
Set up Auto Scaling with Elastic Load Balancing, to automatically distribute incoming application traffic across Amazon EC2 instances within the Auto Scaling groups.

Step 4: Associate the load balancer with the Auto Scaling group.
To distribute traffic of the application across a fleet of EC2 instances that can scale with demand associate the load balancer with the Auto Scaling group.

Step 5: Configure Scaling Policies
Configure scaling policies for the Auto Scaling group.
