#   Project3.md
## Docker Image creation
### Creation of Docker image
#### Instructions

1) Download the given WAR file to a folder /opt/helloworld
2) Create a Docker file in the same folder in the format given below
    FROM tomcat:jre8
    MAINTAINER xxx
    COPY HelloWorld.war /usr/local/tomcat/webapps
3) Build the Docker image using the command below
    docker build -t hellworld .
4) Run the image created above using the command given below
    docker run -d -p 80:8080 helloworld 
5) Verify that the application can be accessed from the machine using the URL below
    <public IP address of instance>/HelloWorld"
Expected screenshots

1) Dockerfile  
2) Building the Docker image. 
3) Running the image 
4) Verification that the application is running ## Upload Image to DockerHub

## Upload Image to DockerHub
#### Instructions
1) Create a new free account at hub.docker.com
2) Create a new public repository in your Dockerhub account
3) Login to the DockerHub account from the CLI using the command below
    docker login --username=<DockerHub username>
4) Tag the image using the command below
     docker tag <image id> <dockerhub username>/<repository name>:latest
5) Push the image to Dockerhub
    docker push <hub-user>/<repo-name>:latest"

Expected screenshots

1) Creation of DockerHub Repository 
2) Logging into DockerHub via CLI
3) Tagging of image 4) Pushing of image to DockerHub




## Creation of ECS cluster to run the image

### a Create the ECS Task, Service and Cluster
#### Instructions
1) Navigate to the ECS service in your AWS Educate account
2) Click on Get Started
3) Under Container Definition, select Custom->Configure
```    Enter the following values
    - Image : docker.io/<dockerhub username>/<dockerhub repository>:latest
    - Memory Limits : 256MB
    - Port Mapping: 8080
    Click on Update and then Next
```
4) Select Load Balancer Type =Application Load Balancer and Click on Next
5) Enter a Cluster Name and Click on Next
6) Click on Create
7) Wait a few minutes for the Cluster to be created"

Expected screenshots
1) Container definition 
2) Service Definition 
3) Configure Cluster



Place Screenshot 1 for Step 4(a) here
Place Screenshot 2 for Step 4(a) here
Place Screenshot 3 for Step 4(a) here


### b Verification of running container on ECS
#### Instructions
1) Navigate to EC2 using the Services Menu
2) Navigate to Load balancer
3) Select the Load Balancer that has been created by the ECS Cluster
4) Take note of the DNS of the load balancer and visit the below URL to verify that the ECS cluster is running the container  
            <DNS of load balancer>:8080/HelloWorld

Expected screenshots
1) Load balancer is created 
2) Verification of URL 


Place Screenshot 1 for Step 4(b) here
Place Screenshot 2 for Step 4(b) here
