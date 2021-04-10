## Remotely Run Commands on an EC2 Instance
<details>
<summary>Click to expand!</summary>
  
### Step 1. Create an Identity and Access Management (IAM) role
<details>

1. Attach Policy AmazonEC2RoleforSSM  
![image](https://user-images.githubusercontent.com/4485129/114269403-7fe2c400-9a24-11eb-95ed-e41128c01a0b.png)

2. Assign name <mark> EnablesEC2ToAccessSystemsManagerRole</mark> to role
![image](https://user-images.githubusercontent.com/4485129/114269442-bd475180-9a24-11eb-9373-71c455d8ac38.png)
3. Create the role.
![image](https://user-images.githubusercontent.com/4485129/114269500-0e574580-9a25-11eb-9140-94c07fbf2b37.png)

</details>


### Step 2. Create an EC2 instance
<details>
1. Attach role IAM Role created above **EnablesEC2ToAccessSystemsManagerRole** to EC2 instance.

![image](https://user-images.githubusercontent.com/4485129/114269580-99d0d680-9a25-11eb-8ec4-d54e0706f443.png)

</details>

### Step 3. Update the Systems Manager Agent
<details>
  
1. Go to AWS Systems Manager -> Fleet Manager -> Managed Instances 
![image](https://user-images.githubusercontent.com/4485129/114269783-5dea4100-9a26-11eb-9bf9-358875f94898.png)

2. Select Node Management -> Run Command
3. Select **AWS-UpdateSSMAgent.** in **Command Document**
![image](https://user-images.githubusercontent.com/4485129/114269922-2039e800-9a27-11eb-8384-a275ba408146.png)

4. Select **Choose instances manually** in **Target**  
![image](https://user-images.githubusercontent.com/4485129/114269974-6ee78200-9a27-11eb-9fec-257c9b6cb00e.png)

5. Click on Run

6. Output 
![image](https://user-images.githubusercontent.com/4485129/114270045-d00f5580-9a27-11eb-9c29-374e1d9f7941.png)

</details>

### Step 4. Run a Remote Shell Script
<details>

![image](https://user-images.githubusercontent.com/4485129/114270359-92133100-9a29-11eb-8456-74d7f41d8041.png)

![image](https://user-images.githubusercontent.com/4485129/114270380-a5be9780-9a29-11eb-899a-3473238dbf11.png)

![image](https://user-images.githubusercontent.com/4485129/114270387-ae16d280-9a29-11eb-8db1-5e41b0532516.png)

![image](https://user-images.githubusercontent.com/4485129/114270403-ba9b2b00-9a29-11eb-9770-75e615fd9c7e.png)

</details>

### Step 5. Terminate Your Resources
<details>

1. A numbered
2. list
   * With some
   * Sub bullets
</details>


</details>


## Set Up a Jenkins Build Server
<details>
<summary>Click to expand!</summary>
 
Introduction

### Step 1: Set Up Prerequisites
<details>
  
1. A numbered
2. list
   * With some
   * Sub bullets
</details>


### Step 2: Launch an EC2 Instance
<details>

1. Create a Security Group for Your Amazon EC2 Instance
2. Launch Your EC2 Instance
   * 1
   * 2
</details>



### Step 3: Install and Configure Jenkins
<details>

1. Connect to Your Linux Instance
![image](https://user-images.githubusercontent.com/4485129/114276033-8d0eab80-9a42-11eb-84b6-76dd7b634553.png)


2. Download and Install Jenkins

* Update the server
```
[ec2-user@ip-172-31-60-53 ~]$ sudo yum update -y
Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
Resolving Dependencies
.........
  python3-pystache.noarch 0:0.5.4-12.amzn2.0.1           python3-setuptools.noarch 0:38.4.0-3.amzn2.0.6           python3-simplejson.x86_64 0:3.2.0-1.amzn2.0.2

Updated:
  amazon-ssm-agent.x86_64 0:3.0.529.0-1.amzn2                                            aws-cfn-bootstrap.noarch 0:2.0-6.amzn2

Complete!
[ec2-user@ip-172-31-60-53 ~]$ 

```

* Install Java8

```
[ec2-user@ip-172-31-60-53 ~]$ sudo yum install java-1.8*
Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
amzn2-core                                                                                                                                         | 3.7 kB  00:00:00     
Resolving Dependencies
--> Running transaction check
---> Package java-1.8.0-openjdk.x86_64 1:1.8.0.282.b08-1.amzn2.0.1 will be installed

....


Complete!
[ec2-user@ip-172-31-60-53 ~]$

```

* Install Jenkins

```
[ec2-user@ip-172-31-60-53 ~]$ sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo
--2021-04-10 15:53:27--  http://pkg.jenkins-ci.org/redhat/jenkins.repo
Resolving pkg.jenkins-ci.org (pkg.jenkins-ci.org)... 52.202.51.185
Connecting to pkg.jenkins-ci.org (pkg.jenkins-ci.org)|52.202.51.185|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 71
Saving to: ‘/etc/yum.repos.d/jenkins.repo’

100%[================================================================================================================================>] 71          --.-K/s   in 0s       

2021-04-10 15:53:27 (12.9 MB/s) - ‘/etc/yum.repos.d/jenkins.repo’ saved [71/71]

[ec2-user@ip-172-31-60-53 ~]$

```

* Start Jenkins 
```

[ec2-user@ip-172-31-60-53 ~]$ sudo service jenkins start

Starting jenkins (via systemctl):                          [  OK  ]
[ec2-user@ip-172-31-60-53 ~]$
```

3. Configure Jenkins
![image](https://user-images.githubusercontent.com/4485129/114276777-cb599a00-9a45-11eb-939a-1ea322768f74.png)


![image](https://user-images.githubusercontent.com/4485129/114276768-c09f0500-9a45-11eb-9b50-296e001a7092.png)

Configure Jenkins Cloud 
![image](https://user-images.githubusercontent.com/4485129/114276991-ccd79200-9a46-11eb-892c-350517290e56.png)

![image](https://user-images.githubusercontent.com/4485129/114277041-11fbc400-9a47-11eb-9c99-b5917ac225f9.png)

![image](https://user-images.githubusercontent.com/4485129/114277214-ed541c00-9a47-11eb-9901-521d37519164.png)

</details>


### Step 5. Step 4: Clean Up
<details>
Terminate EC2 Instance
  
![image](https://user-images.githubusercontent.com/4485129/114277235-f9d87480-9a47-11eb-8def-7ada7ea6713b.png)

1. Additional Resources

</details>
https://aws.amazon.com/blogs/devops/set-up-a-build-pipeline-with-jenkins-and-amazon-ecs/
</details>
