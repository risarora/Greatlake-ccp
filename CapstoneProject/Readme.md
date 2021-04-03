# Capstone Projects as part of GLCCP 

## AWS 

### Capstone 1: 
* Process that needs to be setup to remote manage EC2 instances from an operations perspective.
https://aws.amazon.com/getting-started/hands-on/remotely-run-commands-ec2-instance-systems-manager/

* Build a Jenkins build server for the development team
https://d1.awsstatic.com/Projects/P5505030/aws-project_Jenkins-build-server.pdf?refid=gs_card


### Capstone 2: 
* Migrate a github repository to AWS codecommit
https://docs.aws.amazon.com/codecommit/latest/userguide/how-to-migrate-repository-existing.html

* Setup a compliance archive on Glacier, also include a CLI setup to upload a zip file from local machine to glacier
https://d1.awsstatic.com/Projects/P4113791/aws-project_set-up-compliant-archive.pdf


### Capstone 3: 
* Build a serverless web application using Amplify, Cognito, API Gateway, Lambda & DynamoDB
https://aws.amazon.com/getting-started/hands-on/build-modern-app-fargate-lambda-dynamodb-python/


### Capstone 4: 
This capstone only applies to a developer, this is a slightly more complex case and has many services such as Cloud9, Full codepipeline components, NLB, Fargate, DynamoDB, Lambda, APIGateway, Kinesis, S3, Cognito.
* Build a modern web application in Python
https://aws.amazon.com/getting-started/hands-on/build-modern-app-fargate-lambda-dynamodb-python/


### Capstone 5: 
Perform a heterogeneous database migration from Amazon RDS Oracle to Amazon Aurora with MySQL compatibility using AWS Database Migration Service and the AWS Schema Conversion Tool
* Overview
https://docs.aws.amazon.com/dms/latest/sbs/CHAP_RDSOracle2Aurora.html
* Step-by-step instructions
https://docs.aws.amazon.com/dms/latest/sbs/CHAP_RDSOracle2Aurora.Steps.html


### Capstone 6: 
You will use Amazon EKS to deploy a highly available Kubernetes control plane. You will then configure 'kubectl', an open source command line tool to interact with your Kubernetes infrastructure. Using AWS CloudFormation, you will launch a cluster of worker nodes on Amazon EC2, then launch a containerized guest book application onto your cluster.
* Deploy a Kubernetes Application
https://aws.amazon.com/getting-started/hands-on/deploy-kubernetes-app-amazon-eks/
#### Implementation has 3 steps
  * Cluster Creation
https://docs.aws.amazon.com/eks/latest/userguide/getting-started-console.html
  * Autoscaling
https://docs.aws.amazon.com/eks/latest/userguide/cluster-autoscaler.html
  * Deploy an App
https://docs.aws.amazon.com/eks/latest/userguide/sample-deployment.html


## AZURE

### Capstone 7: 
Deploy a custom Python web app to App Service on Linux, Azure's highly scalable, self-patching web hosting service. You use the local Azure command-line interface (CLI) on a Mac, Linux, or Windows computer.
* Step 1 - https://docs.microsoft.com/en-in/azure/app-service/containers/quickstart-python?tabs=bash
* Step 2 (custom docker image)
https://docs.microsoft.com/en-in/azure/app-service/containers/tutorial-custom-docker-image


### Capstone 8: 
* Host a RESTful API with CORS in Azure App Service.
https://docs.microsoft.com/en-in/azure/app-service/app-service-web-tutorial-rest-api
Azure App Service provides a highly scalable, self-patching web hosting service. In addition, App Service has built-in support for Cross-Origin Resource Sharing (CORS) for RESTful APIs

### Capstone 9: 
Autoscaling a custom application in Azure.
* Create the app
https://docs.microsoft.com/en-in/azure/app-service/app-service-web-get-started-dotnet
* Autoscale the app
https://docs.microsoft.com/en-in/azure/azure-monitor/platform/autoscale-get-started

### Capstone 10:
Azure Data Explorer is a fast and highly scalable data exploration service for log and telemetry data. To use Azure Data Explorer, you first create a cluster, and create one or more databases in that cluster. Then you ingest (load) data into a database so that you can run queries against it. In this quickstart, you create a cluster and a database.
* Step 1 - Create Cluster Database
https://docs.microsoft.com/en-us/azure/data-explorer/create-cluster-database-portal
* Step 2 - Ingest Sample Data
https://docs.microsoft.com/en-us/azure/data-explorer/web-query-data
* Step 3 - Web Query Data
https://docs.microsoft.com/en-us/azure/data-explorer/web-query-data
