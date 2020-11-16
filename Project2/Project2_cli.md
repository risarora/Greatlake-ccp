# Connect to AWS via CLI 

## Install Docker 
## create docker alias
```
alias aws='docker run --rm -it -v ~/.aws:/root/.aws amazon/aws-cli'
```

```
bash-3.2$ aws configure --profile tester
AWS Access Key ID [None]: ******************
AWS Secret Access Key [None]: ******************************
Default region name [None]: ap-south-1
Default output format [None]: json
```

```
bash-3.2$ aws configure list
      Name                    Value             Type    Location
      ----                    -----             ----    --------
   profile                <not set>             None    None
access_key     ****************AEUH shared-credentials-file    
secret_key     ****************hpK3 shared-credentials-file    
    region               ap-south-1      config-file    ~/.aws/config

```

## Create s3 Bucket Source and Target

```
bash-3.2$ aws s3 mb s3://glsource
make_bucket: glsource
bash-3.2$ aws s3 mb s3://gltarget
make_bucket: gltarget
bash-3.2$ aws s3 ls
2020-11-16 20:06:31 glsource
2020-11-16 20:06:40 gltarget

```

## Create SNS Topic 
```
bash-3.2$ aws sns create-topic --name S3toEC2Topic
{
    "TopicArn": "arn:aws:sns:ap-south-1:689161371202:S3toEC2Topic"
}


```

### Modify Access Policy 

```
aws sns add-permission \
--topic-arn arn:aws:sns:ap-south-1:689161371202:S3toEC2Topic \
--aws-account-id 689161371202 \
--label listener \
--action-name Publish

```

# TBD 
## Create s3 Event Notification
```
S3PutEvent
aws put-bucket-notification-configuration \
--bucket s3://glsource \ 
--notification-configuration S3PutEvent \ 
--generate-cli-skeleton 
[--expected-bucket-owner <value>]
[--cli-input-json <value>]
[--generate-cli-skeleton <value>]

```


## Create SNS Listener 
```
subscribe
--topic-arn arn:aws:sns:ap-south-1:689161371202:S3toEC2Topic \
--protocol http \
[--attributes <value>]
[--return-subscription-arn | --no-return-subscription-arn]
[--notification-endpoint <value>]
[--cli-input-json <value>]
[--generate-cli-skeleton <value>]

     Name : S3PutEvent
     Select PUT from the list of radio buttons
     Destination : Select SNS Topic
     SNS : Select S3ToEC2Topic



```

## Create IAM  
```

```
## Create Ec2 
```

```
Configure Ec2 Server

Copy file to s3 Source

## Create Athena DB 
```

```
## Create Athena Table 
```

```
Run Select Query on Athena


# Cleanup
aws s3 rb s3://glsource
aws s3 rb s3://gltarget
aws s3 ls 
aws sns delete-topic --topic-arn arn:aws:sns:ap-south-1:689161371202:S3toEC2Topic
