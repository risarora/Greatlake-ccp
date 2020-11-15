# MCQs
## Answer the following questions - 1 marks each 
Q1	Which of the following properties of an AWS resource is sufficient and necessary to uniquely identify it across all of AWS?
- [x] ARN
- [ ] Re and ARN
- [ ] ARN and Account number
- [ ] Depends on the resource used

	
Q2	Which of the following services are available when creating a new table with Athena
- [ ] RDS and S3
- [x] S3 and AW Glue
- [ ] RDS and EBS
- [ ] S3 and EBS

	
Q3	Which of the following step numbers in Step 2 allowed S3 to publish to the SNS topic created?
- [ ] 2(a)
- [ ] 2(c)
- [x] 2(d)
- [ ] 2(b)

	
Q4	Which port is being used by SNS to send the notification to the custom program?
- [ ] 8081
- [ ] 80
- [x] 8080
- [ ] 8065

	
Q5	How many IAM roles can be attached to an EC2 instance at a time?
- [ ] 2
- [ ] 3
- [x] 1
- [ ] Depends on the policies required


Q6	As a product manager, how would you describe the benefits of this architecture to an client, as compared to an equivalent on-premises architecture?	5


# Step 2 - S3 and SNS topic creation

### Step number	a

#### Step name	Creation of Source  and target buckets

**Instructions**	
1) Navigate to S3 using the Services button at the top of the screenSelect 'Create Bucket' 
2) Enter a source bucket name and use the default options for the rest of the fields
3) Click on 'Create Bucket'
4) Repeat the above steps to create a target bucket

**Expected screenshots**
1) Screen showing created S3 source and target buckets


	Place Screenshot for Step 2(a)
![](./images/2020-11-14-14-22-44.png)

	
### Step number	b

#### Step name	Creation of SNS subscription

**Instructions**	
1) Navigate to SNS -> TopicsClick on 'Create Topic'
3) Enter the following fields
    Name : S3toEC2Topic
    The other options can b ignored for now
4) Click on Create Topic

**Expected screenshots**
1) Creation of SNS topic


	Place Screenshot for Step 2(b)
![](./images/2020-11-14-14-26-01.png)

### Step number	c

#### Step name	Modification of SNS Access Policy 

**Instructions**	
1) Navigate to SNS -> Topics and select the topic created in the previous stepNote down the ARN shown in the topic details
2) Click on Edit and select 'Access Policy'.
3) Replace the text in the JSON editor with the followin
```
{
 "Version": "2012-10-17",
 "Id": "example-ID",
 "Statement": [
  {
   "Sid": "example-statement-ID",
   "Effect": "Allow",
   "Principal": {
    "AWS":"*"  
   },
   "Action": [
    "SNS:Publish"
   ],
   "Resource": "arn:aws:sns:us-east-1:916317828206:S3toEC2Topic",
   "Condition": {
      "ArnLike": { "aws:SourceArn": "arn:aws:s3:*:*:glsource" },
      "StringEquals": { "aws:SourceAccount": "916317828206" }
   }
  }
 ]
}
```

// arn:aws:sts::916317828206:assumed-role/vocstartsoft/user1025256=risarora@gmail.com

1) Replace the bold text with the SNS topic ARN, source bucket name and your AWS account ID respectively.      
2) Click on Save Changes

**Expected screenshots**
1) JSON Editor screen

![](./images/2020-11-14-14-58-31.png)
	Place Screenshot for Step 2(c)

### Step number	d
#### Step name	Configuring SNS notifications for S3
Instructions	"1) Navigate to S3 and select the source bucket created in Step 1 (a)
2) Select Properties and scroll down to Event Notifications and select it
3) Select ""Create Event Notification""
4) Fillup the details as follows 
     Name : S3PutEvent
     Select PUT from the list of radio buttons
     Destination : Select SNS Topic
     SNS : Select S3ToEC2Topic
     
5) Save Changes"
Expected screenshots	1) Event Configuration Screen
![](./images/2020-11-15-13-41-47.png)

# Step 3 - Run the custom program on the EC2 instance
	
### Step number	a

#### Step name	Creation of the EC2 instance

**Instructions**	
1) Navigate to EC2 -> InstancesCreate an EC2 instance with the following parameters
     AMI : Ubuntu 18.04 LTS
     VPC : Default
     Security group : Ports 22and 8080 should be opened

**Expected screenshots**
1) List of instances after creation of EC2 instance


	Place Screenshot for Step 3(a)
![](./images/2020-11-14-16-01-09.png)

### Step number	b

#### Step name	Creation of IAM role for EC2 instance

**Instructions**	
1) Navigate to IAM- > RolesSelect Create Role
3) Use the following parameters to create the role
     Trusted Entity  - AWS Service
     Use Case - EC
     Policies to attach - Amazon S3 Full Access and AmazonDynamoDBFullAccess
     Role Name : ec2-s3-access
4) Click on Create Role
5) Navigate back to EC2- > Instances
6) Select the EC2 instance created in the previous step and select Actions-> Security -> Modify IAM role
7) Select the role ec2-s3-access from the dropdown and click on Save

**Expected screenshots**
1) Modify IAM role screen
![](./images/2020-11-15-12-36-06.png)
![](./images/2020-11-14-16-24-46.png)
![](./images/2020-11-14-16-25-15.png)

	Place Screenshot for Step 3(b)
	
### Step number	c

#### Step name	Configuration and Uploading of custom program
**Instructions**	
1) Open the drive link given under Architecture implementation in Step 1 and download the file docproc-new.zip on your machine
2) Unzip the downloaded file
3) Enter the unzipped folder and open the file views.py in the API folder using a text editor
4) In line number 19, modify the target bucket name to the one created in Step 2 (a) and save the file
5) Copy the folder docproc-new to the home folder of the EC2 instance created in Step 3(a) using scp. Use the command given below
```
chmod 400 glccp.pem
scp -i glccp.pem -r ./docproc-new ubuntu@54.146.93.185:/home/ubuntu
```

**Expected screenshots**
1) Modifying of the views.py file to point to the target bucket
![](./images/2020-11-14-16-47-59.png)
2) Copying the folder to the EC2 instance	
![](./images/2020-11-14-16-47-25.png)

# Step 4 - Creation and Verification of SNS subscription and Generation of CSV file
	
### Step number	a

#### Step name	Starting the EC2 custom program

**Instructions**	
1) Log into the EC2 instance using SSH
```
bash-3.2$ ssh -i "$HOME/Desktop/glccp.pem" ubuntu@ec2-54-146-93-185.compute-1.amazonaws.com
```
2) Run the followng commands after successful SSH to start the server

```
    sudo cp -r docproc-new /opt
    sudo chown ubuntu:ubuntu -R /opt 
    cd /opt/docproc-new
    sudo apt update
    sudo apt install python-pip -y
    python -m pip install --upgrade pip setuptools
    sudo apt install virtualenv -y
    virtualenv ~/.virtualenvs/djangodev
    source ~/.virtualenvs/djangodev/bin/activate
    pip install django
    pip install boto3
    python manage.py runserver 0:8080
```
Keep this terminal window open throughout the rest of the exercise

**Expected screenshots**
1) Server in waiting state
Place Screenshot for Step 4(a)
![](./images/2020-11-14-16-54-47.png)

### Step number	b

#### Step name	Creation of SNS subscription
**Instructions**	
1) Navigate to SNS in the AWS Console and select the topic S3ToEC2Topic
2) Click on Create Subscription
3) Enter the following details
     Protocol : HTTP
     Endpoint : http://54.146.93.185:8080/sns where 54.146.93.185 in the public IP of the EC2 instance
     Click on Create Subscription
4) In the EC2 terminal window, look for the field 'SubscribeURL' and copy the entire link given
Note: If a message is seen 'ValueError: No JSON object could be decoded', it can be safely ignored
5) Paste that link into a browser window to verify the SNS subscription (Ignore any messages received in the web browser)

**Expected screenshots**
1) Subscription URL in EC2 terminal Window

![](./images/2020-11-14-16-58-44.png)
	Place Screenshot for Step 4(b)
	
### Step number	c

#### Step name	Generation of CSV file
**Instructions**	
1) Download the file docproc-invoice.txt in the drive link given in step 1
2) Navigate to S3 in the AWS Console
3) Upload the sample invoice file to the source S3 bucket using the default options
4) Verify that a CSV file is generated in the target S3 bucket. This may take a few minutes 

**Expected screenshots**
1) Generated CSV file in the target S3 bucket
![](./images/2020-11-15-13-45-46.png)
Place Screenshot for Step 4(c)
	
### Step number	d

#### Step name	Table creation in DynamoDB

**Instructions**	
1) Navigate to DynamoDB using the Services MenuClick on tables on the left side
3) Select the table 'invoice'
4) Click on the 'Items' tab and verify that a record has been created in the table with the contents of the invoice file. 

**Expected screenshots**
1) Items tab showing the table records
![](./images/2020-11-15-13-47-11.png)
Place Screenshot for Step 4(d)


# Step 5 - Querying the CSV file using Athena

### Step number a										
Step name	Querying the CSV file using Athena																								
Instructions	
1) Navigate to AWS Athena in the AWS Console
2) Use the following command in the query editor to create a database
```
create database proj2db;
```
3) Run the following query to create the table based on the generated CSV file
```
CREATE EXTERNAL TABLE IF NOT EXISTS proj2db.invoice (
  `customer_id` string,
  `inv_id` string,
  `date` string,
  `from` string,
  `to` string,
  `amount` float,
  `sgst` float,
  `total` float,
  `inwords` string 
)
ROW FORMAT SERDE 'org.apache.hadoop.hive.serde2.lazy.LazySimpleSerDe'
WITH SERDEPROPERTIES (
  'serialization.format' = ',',
  'field.delim' = ','
) LOCATION 's3://gltarget/'
TBLPROPERTIES ('has_encrypted_data'='false');

```

Remember to replace the name of the target S3 bucket in the above query

4) Run the following query to show aggregated expenses by date

```
SELECT sum('amount'), 'date' FROM 'proj2db'.'invoice' GROUP BY 'date';
```

**Expected screenshots**

1) Creation of database	
Place Screenshot 1 for Step 5(a)
![](./images/2020-11-15-14-59-44.png)
2) Creation of Table	
Place Screenshot 2 for Step 5(a)
![](./images/2020-11-15-14-49-39.png)
1) Query to show aggregated expenses																
Place Screenshot 3 for Step 5(a)
![](./images/2020-11-15-14-51-42.png)