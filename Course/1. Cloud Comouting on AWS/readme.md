
## Week 1 - Learning Material - Compute, Organization & IAM (~ 3.5 Hours)

<details>
  <summary>Click to expand!</summary>
 
### Module 1 - Core Building Blocks, Abstraction, AWS Console (~20mins)
### Module 2 - Compute - Elastic Compute Cloud or EC2 (~1hr)
### Module 2a - AWS EC2 Step 3 - Advanced Features Part I (~25mins
### Module 2b - AWS EC2 Step 3 - Advanced Features Part II (~10
### Module 3 - How to SSH in to an EC2 Instance (~15mins)
### Module 4 - Load Balancing, Fault Tolerance & CloudWatch(~1hr)
### Module 5 - Windows EC2 Instance, Instance Pricing (~ 15mins)
### Module 6 - Identity & Access Management (~15mins)

</details>

## Week 2 - Learning Material - Auto Scaling, AMI, AWS CLI & Storage (~ 6 Hours)
<details>
  <summary>Click to expand!</summary>

## Autoscaling
 <details>
  <summary>Click to expand!</summary>

### Module 7a - Auto scaling principles (~10mins)
### Module 7b - Launch Templates (~30mins)
### Module 7c - Auto scaling group Part1 (~20mins)
### Module 7d - Auto scaling group Part2 (~20mins)
### Module 7e - Auto scaling group Part3 (~30mins)
### Module 7f - Self healing (~5mins)
### Module 7g - Cleanup
### Module 7h - Auto Scaling [Old UI] (~1hr)

[DIY _ Mounting S3 on local filesystem using S3FS-FUSE .pdf](https://github.com/risarora/Greatlake-ccp/files/6279920/DIY._.Mounting.S3.on.local.filesystem.using.S3FS-FUSE.pdf)

#### S3 Transition options

<details>
You can add rules in an S3 Lifecycle configuration to tell Amazon S3 to transition objects to another Amazon S3 storage class. For example:

When you know that objects are infrequently accessed, you might transition them to the S3 Standard-IA storage class.

You might want to archive objects that you don't need to access in real time to the S3 Glacier storage class.

In an S3 Lifecycle configuration, you can define rules to transition objects from one storage class to another to save on storage costs. When you don't know the access patterns of your objects, or your access patterns are changing over time, you can transition the objects to the S3 Intelligent-Tiering storage class for automatic cost savings.

</details>

#### Mounting S3 on local filesystem
<details>
Any application interacting with the mounted drive doesn’t have to worry about transfer protocols, security mechanisms, or Amazon S3-specific API calls. In some cases, mounting Amazon S3 as drive on an application server can make creating a distributed file store extremely easy.

For example, when creating a photo upload application, you can have it store data on a fixed path in a file system and when deploying you can mount an Amazon S3 bucket on that fixed path. This way, the application will write all files in the bucket without you having to worry about Amazon S3 integration at the application level. Another major advantage is to enable legacy applications to scale in the cloud since there are no source code changes required to use an Amazon S3 bucket as storage backend: the application can be configured to use a local path where the Amazon S3 bucket is mounted. This technique is also very helpful when you want to collect logs from various servers in a central location for archiving.

S3FS-FUSE: This is a free, open-source FUSE plugin and an easy-to-use utility which supports major Linux distributions & MacOS. S3FS also takes care of caching files locally to improve performance. This plugin simply shows the Amazon S3 bucket as a drive on your system.

Read more here https://github.com/s3fs-fuse/s3fs-fuse

Important - Generally S3 cannot offer the same performance or semantics as a local file system.

This is for additional reference only.

</details>
</details>

## AMI and CLI
<details>
  <summary>Click to expand!</summary>

### Module 8 - Amazon Machine Image or AMI (~15mins)
### Module 9 - AWS Command Line Interface (~40mins)
</details>

## Storage
<details>
  <summary>Click to expand!</summary>

### Module 10 - Forms of Storage on Cloud(~15mins)
### Module 11 - Block Storage - EBS(~30mins)
### Module 12 - Elastic File System(~15mins)
### Module 13 - Object Storage - Simple Storage Service(~1hr15mins)
</details>
</details>

## Week 3 - Learning Material - VPC, Route53, WAF (~ 4 Hours)
<details>
  <summary>Click to expand!</summary>
 
### Module 14 - Overview of Virtual Private Cloud - VPC (~20mins)
### Module 15 - Hybrid Cloud & Networking(~20mins)
### Module 16 - Walk-through AWS VPC Console(~10mins)
### Module 17 - Creating & Using VPC - A Step by Step Use Case
### Module 18 - VPC Peering(~15mins)
### Module 19 - VPC EndPoints, Services & Route 53(~10mins)
### Module 20 - Route 53 Demo(~5mins)
### Module 21 - Web Application Firewall Classic (~1hr)
### Module 22 - AWS WAF - Next Generation (~40mins)

</details>
