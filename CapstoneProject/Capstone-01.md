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
2. Download and Install Jenkins
3. Configure Jenkins
</details>


### Step 5. Step 4: Clean Up
<details>

1. Additional Resources

</details>

</details>
