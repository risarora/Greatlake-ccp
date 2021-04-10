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


## Overview 
### Architecture
![image](https://user-images.githubusercontent.com/4485129/114260255-5492b180-99f1-11eb-8eb5-6c1255e81a39.png)

### Objective 
To deploy a containerized application onto a Kubernetes cluster managed by Amazon Elastic Container Service for Kubernetes (Amazon EKS)

### Cost to complete:  
This tutorial will cost you less than $0.60*.
 
### Technologies used:
* An active AWS account**
* Amazon EKS
* Elastic Load Balancing
* kubectl


## Steps 
#### Configure aws cli
![image](https://user-images.githubusercontent.com/4485129/114265058-4900b400-9a0c-11eb-816f-867658d3dfe0.png)

#### Create an Amazon VPC with public and private subnets that meets Amazon EKS requirements.
```
PS D:\Cloud\aws-CLI> aws cloudformation create-stack --stack-name my-eks-vpc-stack --template-url https://s3.us-west-2.amazonaws.com/amazon-eks/cloudformation/2020-10-29/amazon-eks-vpc-private-subnets.yaml
```

* AWS CLI
![image](https://user-images.githubusercontent.com/4485129/114265225-45b9f800-9a0d-11eb-8fb2-b7ca5df8205b.png)

* AWS Console 
![image](https://user-images.githubusercontent.com/4485129/114265268-78fc8700-9a0d-11eb-8e39-6cb541499b49.png)

![image](https://user-images.githubusercontent.com/4485129/114265283-97fb1900-9a0d-11eb-9d08-e7bfe7c6fe3f.png)


##### Create a cluster IAM role and attach the required Amazon EKS IAM managed policy to it.

a. Copy the following contents to a file named cluster-role-trust-policy.json.
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "eks.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

* Create the role
```
aws iam create-role --role-name myAmazonEKSClusterRole --assume-role-policy-document file://"cluster-role-trust-policy.json"
``` 
![image](https://user-images.githubusercontent.com/4485129/114265461-7f3f3300-9a0e-11eb-97fa-885f045891e3.png)

* Attach the required Amazon EKS managed IAM policy to the role.
```
aws iam attach-role-policy \
  --policy-arn arn:aws:iam::aws:policy/AmazonEKSClusterPolicy \
  --role-name myAmazonEKSClusterRole
 ```

##### Create Cluster EKS 
* Open the Amazon EKS console at https://console.aws.amazon.com/eks/home#/clusters.


![image](https://user-images.githubusercontent.com/4485129/114264978-bfe97d00-9a0b-11eb-99e4-1f67b259a9a2.png)
