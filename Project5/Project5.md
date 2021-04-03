Step 1 : Virtual Machine Creation



Step number	a
Step name	Creation of Virtual Machine
Instructions	1) Login to the Azure portal of your Azure account
2) Use the search bar at the top of the screen to navigate to Resource groups 
3) Select “New” and create a resource group in any region of your choice
4) Navigate to Virtual Machines using the search bar and select “Add”
5) Create a virtual machine in the created Resource Group using the specifications given below:
Instance:Windows 2019 Data Center
VM Size: DS1- v2
Inbound ports : 3389, 80 and 443. (Same ports to be allowed for network interface)
Authentication type: Password
Load Balancing : No
Rest of the options can be left as default


Expected screenshots	1) Created Resource Group 2) Created Virtual Machine . 


<Insert screenshot for a(1) here>

Resource Group 
![image](https://user-images.githubusercontent.com/4485129/113468761-d456d400-9465-11eb-9f9d-024b49ba80ed.png)

 




Virtual Machine
![image](https://user-images.githubusercontent.com/4485129/113468763-d9b41e80-9465-11eb-92b8-c5dcd516ca4c.png)

 

 
Step 2: Installation of IIS

Step number	a	
Step name	Installation of IIS server	
Instructions	1) Navigate to the VM created in the previous step.

2) Connect to the VM using RDP. You can check the link below to learn how to do so
https://docs.microsoft.com/en-us/azure/virtual-machines/windows/connect-logon
Note that Windows users will already have an RDP client installed, while Linux and macOS users will need to install a client such as Remmina or Microsoft Remote Desktop

3) Once the RDP connection has been made, open the PowerShell application in the VM.

4) Install IIS in the VM by entering the below command in the PowerShell
Install-WindowsFeature -name Web-Server -IncludeManagementTools

5) Ensure IIS is working correctly by access the public IP address of the VM in a web browser 

	
Expected screenshots	1) RDP into the instance 2) Installation of IIS using the command
3) Verification of IIS installation	

<Insert screenshot for a(1) here>
 ![image](https://user-images.githubusercontent.com/4485129/113468768-e173c300-9465-11eb-9218-390702359647.png)

 
<Insert screenshot for a(2) here>

 ![image](https://user-images.githubusercontent.com/4485129/113468773-e46eb380-9465-11eb-90d6-a9c8ca2a5ac1.png)


<Insert screenshot for a(3) here>

 ![image](https://user-images.githubusercontent.com/4485129/113468776-e89ad100-9465-11eb-8a69-b6938a913e2d.png)





Step 3: Use Traffic Manager

Step number	a			
Step name	Installation and Configuration of Traffic Manager			
Instructions	1) In the Azure portal, navigate to the Virtual Machine created previously and go to the Overview page.  
2) Under DNS name, click on Configure
3) Enter a DNS name label and click on Save. 
4) Navigate to Traffic Manager profiles using the search bar. 
5) Create the profile in the same Resource group as created previously. The routing method has to be set to Performance
6) Navigate to the created Traffic Manager profile and go to the Endpoints page. 
7) Click on Add and add the endpoint with the following details
Type : Azure Endpoint
Target Resource Type : Public IP address
Public IP address : Select the IP address of the VM from the drop-down list. 
Rest of the fields can be left to the default values.  
8) Navigate back to the Overview Page
9) Access the Traffic Manager’s DNS name from a web browser to verify that the web server is being accessed
Expected screenshots	1) Configuration of DNS Name for VM 2) Creation of Traffic Manager Profile 3) Adding of endpoint to the Traffic Manager profile 4) Accessing the webserver via the Traffic Manager

<Insert screenshot for a(1) here>
 ![image](https://user-images.githubusercontent.com/4485129/113468778-ec2e5800-9465-11eb-918a-4a1e35f6e6de.png)



<Insert screenshot for a(2) here>
 ![image](https://user-images.githubusercontent.com/4485129/113468781-efc1df00-9465-11eb-845f-901787241e55.png)


<Insert screenshot for a(3) here>
 ![image](https://user-images.githubusercontent.com/4485129/113468786-f5b7c000-9465-11eb-98b8-0f21e648b500.png)



 
<Insert screenshot for a(4) here>
 ![image](https://user-images.githubusercontent.com/4485129/113468787-f94b4700-9465-11eb-87a4-60fcab60accf.png)















 
Step 4 : Modification of IIS home page. 

Step number	a			
Step name	Modification of IIS home page			
Instructions	1) Login into the created VM using RDP
2) Using the file explorer in the VM , navigate to C:\inetpub\wwwroot
3) Create a file called index.html
4) Insert the following text in the index.html file
<html>
<body>
Welcome to Great Learning YourNameHere. This is your Web server.
</body>
</html>
5) Save the file and access the web server again via the Traffic Manager to verify that the modified home page is being displayed.
Expected screenshots	1) Contents of Index.html
2) Modified home page		


<Insert screenshot for a(1) here>
 ![image](https://user-images.githubusercontent.com/4485129/113468793-fe0ffb00-9465-11eb-8f85-faa38da2fac5.png)





<Insert screenshot for a(2) here>

![image](https://user-images.githubusercontent.com/4485129/113468795-01a38200-9466-11eb-86c9-ba71c8e94d74.png)

 








