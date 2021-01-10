# Create a cassandra cluster and check data availibity
## Cassandra Cluster Creation and Configuration	
	
### Instructions	
1) Create a new security group by the name `cassandra-ports`
     `Custom TCP`and port range of `1024-65500` and port 22 for SSH

2) Create 3 EC2 instances (t2-small) using the 7 step workflow
* Use the `SKL-Ubuntu-Cassandra` (community AMI) in AZ1, AZ2, AZ3
* The AMI contains `Ubuntu 16.04, JDK8, Python2.7 & unconfigured Cassandra`
* Assign the `cassandra-ports` SG
* Make sure to name the instances as instance 1, 2, and 3 to make it easier to keep track of them
 
3) Follow the steps to configure Cassandra (repeat this in all instances) by logging in via SSH into each of the instances

* Go to the `conf` folder and update the cassandra.yaml using the commands below
```
cd /opt/apache-cassandra-3.11.1/conf
sed -i 's=MOD_CLUSTER_NAME=GL-Cluster=g' cassandra.yaml
sed -i 's=MOD_IP_ADDRESS=[LOCAL IP here]=g' cassandra.yaml
sed -i 's=MOD_SEED_LIST=[SEED IP here]=g' cassandra.yaml

sed -i 's=MOD_DATACENTER=dc1=g' cassandra-rackdc.properties
sed -i 's=MOD_RACK=[RACK 1,2,3]=g' cassandra-rackdc.properties (r1 for instance 1, r2 for instance 2 and r3 for instance 3)
```
* Example commands for the above are shown below (THESE COMMANDS ARE JUST AN EXAMPLE AND WILL NOT WORK IN YOUR SETUP)

```
    sed -i 's=MOD_IP_ADDRESS=172.31.39.217=g' cassandra.yaml
    sed -i 's=MOD_CLUSTER_NAME=GL-Cluster=g' cassandra.yaml
    sed -i 's=MOD_SEED_LIST=172.31.43.230=g' cassandra.yaml
    sed -i 's=MOD_DATACENTER=dc1=g' cassandra-rackdc.properties
    sed -i 's=MOD_RACK=r2=g' cassandra-rackdc.properties
```
* Start the Cassandra Daemon in each instance using the commands below
```
cd /opt/apache-cassandra-3.11.1/bin
./cassandra
./nodetool status
```
Expected Screenshots : 
1) EC2 screen showing all 3 instances after creations 
2) Cassandra configuration commands on Instance 2
3) Nodetool status output for instance 1

## Uploading of Sample Data	
	
### Instructions	
1) Login to cqlsh in instance 1 by logging into it via SSH and running the below command
```
cd /opt/apache-cassandra-3.11.1/bin
./cqlsh <EC2 private IP> -u cassandra -p cassandra
```
2) Ensure the `system_auth` keyspace replication is changed using the command below
```
    ALTER KEYSPACE `system_auth` WITH REPLICATION = {'class':'NetworkTopologyStrategy', 'dc1':3};
```
3) Create a keyspace and sample table using the command below
```
    CREATE KEYSPACE IF NOT EXISTS starfleet WITH replication = {'class':'NetworkTopologyStrategy', 'dc1':3};

  CREATE TABLE starfleet.user (
       user_id VARCHAR,
       location VARCHAR,
       display_name VARCHAR,
       first_name VARCHAR,
       last_name VARCHAR,
       PRIMARY KEY (user_id, location)
  );
```
4) Insert 2 records into the table using the commands below
```
   INSERT INTO starfleet.user (user_id,location,display_name,first_name,last_name)
   VALUES ('u1','earth1','Kirk','William','Shatner');

   INSERT INTO starfleet.user (user_id,location,display_name,first_name,last_name)
   VALUES ('u2','vulcan','Spock','Leonard','Nimoy');
``` 
Required Screenshots : 
1) Logging into cqlsh 
2) Creation of user table
3) Inserting of the data records 


## Check and modify the consistency levels of the cluster			
Instructions	
1) Login to cqlsh of instance 1 as done previously
2) Check the consistency level of the cluster with the command below
    ```
    CONSISTENCY
    ```

3) Set the consistency level to ALL with the command below
    ```
    CONSISTENCY ALL
    ```
4) Run the following SQL command
    ```
    select * from starfleet.user where user_id = 'u2';
    ```

5) Shut down node 3 with by logging in via SSH to instance 3 and running the command below
    ```
     cd /opt/apache-cassandra-3.11.1/bin
     ./nodetool stopdaemon
    ```
6) Go back to the cqlsh shell of instance 1 and run the above SQL command again

7) Set the consistency level to QUORUM and run the SQL command again

Expected screenshots	

1) Initial Consistency Level 
2) Setting Consistency level to ALL 
3) Output of SQL command with consistency level all after shutting down node 3
4) Setting consistency level to QUORUM and SQL output