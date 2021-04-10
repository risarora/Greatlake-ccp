# Capstone 6:
You will use Amazon EKS to deploy a highly available Kubernetes control plane. 
You will then configure 'kubectl', an open source command line tool to interact with your Kubernetes infrastructure. 
Using AWS CloudFormation, you will launch a cluster of worker nodes on Amazon EC2, then launch a containerized guest book application onto your cluster.

## Steps
Deploy a Kubernetes Application https://aws.amazon.com/getting-started/hands-on/deploy-kubernetes-app-amazon-eks/
Implementation has 3 steps
* Cluster Creation https://docs.aws.amazon.com/eks/latest/userguide/getting-started-console.html
* Autoscaling https://docs.aws.amazon.com/eks/latest/userguide/cluster-autoscaler.html
* Deploy an App https://docs.aws.amazon.com/eks/latest/userguide/sample-deployment.html

## Architecture
![image](https://user-images.githubusercontent.com/4485129/114260255-5492b180-99f1-11eb-8eb5-6c1255e81a39.png)

## Objective 
To deploy a containerized application onto a Kubernetes cluster managed by Amazon Elastic Container Service for Kubernetes (Amazon EKS)

## Cost to complete:  
This tutorial will cost you less than $0.60*.
 
## Technologies used:
* An active AWS account**
* Amazon EKS
* Elastic Load Balancing
* kubectl
