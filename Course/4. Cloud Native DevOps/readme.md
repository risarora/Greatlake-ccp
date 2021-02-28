# Cloud Native DevOps

## Week 1 - Learning Material - DevOps on AWS (~4Hr 30mins)
<details>
  <summary>Click to expand!</summary>
 
### Module 1 - AWS Cloud Trail(~10mins)-3
### Module 2 - AWS Storage Gateway (~15mins)-3
### Module 3 - Operations Workflow overview (~6mins)-3
### Module 4 - Operations Workflow details (~15mins)-3
### Module 5 - Setup EC2(Dev), IAM (~10mins)-3
### CodeCommit
<details>
  <summary>Click to expand!</summary>

### Module 6 - CodeCommit Repo, Opsroot User (~10mins)-3
### Module 7 - Setup SSH, GitClone (~15mins)-3
### Module 8 - Code Setup, GitPush (~10mins)-3

### CodeCommit commands-3
<details>
  <summary>Click to expand!</summary>
 
```
Codebase synch commands

mkdir /opt/temp
cd /opt/temp
To be executed on your local laptop
scp -i your.pem HelloWorld-CodeBase.tar.gz ubuntu@PUBLIC-IP:/opt/temp
tar -zxf HelloWorld-CodeBase.tar.gz
cd HelloWorld
rm -rf .git
rsync -r /opt/temp/HelloWorld/ /opt/helloworld
cd /opt/helloworld
rm -rf /opt/temp
Git commands

cd /opt/helloworld
git add .
git status
git commit -a -m “First commit”
git push origin master

```
</details>

</details>

### CodeBuild
<details>
  <summary>Click to expand!</summary>

### Module 9 - CodeBuild Principles (~15mins)-2
### Module 10 - CodeBuild Project Setup (~20mins)-2
### Module 11 - Run Build Manually (~5mins)-2
</details>

### CodeDeploy
<details>
  <summary>Click to expand!</summary>

### Module 12 - CodeDeploy Principles (~5mins)-2
### Module 13 - EC2(prod), CodeDeploy Service Role (~10mins)-2
### Module 14 - CodeDeploy Agent Installation (~10mins)-2
### Module 15 - CodeDeploy Service Setup (~15mins)-2
CodeDeploy commands-2
<details>
  <summary>Click to expand!</summary>

CodeDeploy agent installation (Prod EC2 instance)
```
sudo chown ubuntu:ubuntu -R /opt
cd /opt
sudo apt install ruby -y
cd /opt
Execute any one command (demonstrating two possible options)
wget https://aws-codedeploy-us-west-2.s3.amazonaws.com/latest/install
wget https://aws-codedeploy-us-west-2.s3.us-west-2.amazonaws.com/latest/install
chmod +x ./install
sudo ./install auto
After installation steps

Stop and start (multiple times) and then you will see the service running

sudo service codedeploy-agent status
sudo service codedeploy-agent stop
sudo service codedeploy-agent start
```
Agent logs
```
tail -30 /var/log/aws/codedeploy-agent/codedeploy-agent.log
```
</details>
</details>


### CodePipeline
<details>
  <summary>Click to expand!</summary>

### Module 16 - CodePipeline Setup (~15mins)-2
### Module 17 - Pipeline execution, Human approval (~15mins)-2
### Module 18 - Build env, Error simulation with pipeline (~10mins)-2
* DIY - Creating CodePipeline
* IaaS app deployment automation
### Module 19 - Elastic Beanstalk (~1Hr)-2

</details>
</details>

## Week 2 - Cloud Formation and Terraform (~4 Hrs)
<details>
  <summary>Click to expand!</summary>

### Module 20 - AWS Cloud Formation Overview (~ 20 mins)-3
### Module 21 - AWS Cloud Formation Template and Demo (~1 hour)-3

* DIY - Cloud Formation
* CF1.json
* CF2.json

### Module 22 - Terraform Essentials (1Hr 15Mins)-3
### Module 23 - Terraform templating and trouble shooting (~1hr 30mins)-3

</details>
