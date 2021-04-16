## Week 2 - Learning Material - Auto Scaling, AMI, AWS CLI & Storage (~ 6 Hours)

## Autoscaling
 <details>
  <summary>Click to expand!</summary>

### Module 7a - Auto scaling principles (~10mins)
### Module 7b - Launch Templates (~30mins)
* User Data
```
#!/bin/bash
apt update -y
apt install apache2 -y
service apache2 start
IP_ADDR=${curl http://169.254.169.254/latest/meta-data/public-ipv4}
echo "Auto scale instance "$IP_ADDR > /var/www/html/index.htm
echo "ok" > /var/www/html/health.htm
```

### Module 7c - Auto scaling group Part1 (~20mins)
### Module 7d - Auto scaling group Part2 (~20mins)
### Module 7e - Auto scaling group Part3 (~30mins)
### Module 7f - Self healing (~5mins)
### Module 7g - Cleanup
### Module 7h - Auto Scaling [Old UI] (~1hr)

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
* **Instance Storage** - Native storage internal to **EC2**
* **Block Storage** aka **EBS** 
* **File System** 
* **Object Based Storage**
### Module 11 - Elastic Block Storage - EBS(~30mins)
* One to one mapping to EC2
* Same AZ as EC2 machine 
* Fixed size

![image](https://user-images.githubusercontent.com/4485129/114986596-cff0d900-9eb1-11eb-9973-a17663d0408f.png)

```
PS D:\Cloud\Projects\Project1> aws ebs start-snapshot --volume-size 100000

An error occurred (ValidationException) when calling the StartSnapshot operation: Invalid volume size: 100000
PS D:\Cloud\Projects\Project1> aws ebs start-snapshot --volume-size 10    
{
    "SnapshotId": "snap-049409d3d1e98658a",
    "OwnerId": "689161371202",
    "Status": "pending",
    "StartTime": "2021-04-16T13:23:02.442000+05:30",
    "VolumeSize": 10,
    "BlockSize": 524288
}

PS D:\Cloud\Projects\Project1>                                            
```
![image](https://user-images.githubusercontent.com/4485129/114991547-522fcc00-9eb7-11eb-80e5-0aa0f148ff07.png)


### Module 12 - Elastic File System(~15mins)
* One to many mapping with EC2
* Elastic Size i.e. expanding
* Can be Mounted on multiple EC2 machines in read write mode. 
### Module 13 - Object Storage - Simple Storage Service(~1hr15mins)
Drop file to S3, API available to access files stored on S3 

* Object Based Storage 
* Object Life Cycle
* Versionining
* Bucket Creation, Access, Policies
* Cross Region Replication
* S3 Events

![image](https://user-images.githubusercontent.com/4485129/114984841-c0709080-9eaf-11eb-93fe-e2a2b280bbea.png)

### S3 Reference
<details>
 
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

