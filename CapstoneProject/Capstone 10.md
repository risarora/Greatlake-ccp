## Capstone 10:
Azure Data Explorer is a fast and highly scalable data exploration service for log and telemetry data. To use Azure Data Explorer, you first create a cluster, and create one or more databases in that cluster. Then you ingest (load) data into a database so that you can run queries against it. In this quickstart, you create a cluster and a database.

### Step 1 - Create Cluster Database https://docs.microsoft.com/en-us/azure/data-explorer/create-cluster-database-portal
<details>
  
#### Azure Data Explorer

![image](https://user-images.githubusercontent.com/4485129/113469767-edfc1980-946d-11eb-9843-67359a7beafa.png)

1. Create Azure Data Explorer

![image](https://user-images.githubusercontent.com/4485129/113470128-c5295380-9470-11eb-8f60-0c8fb93661cd.png)
<br>
![image](https://user-images.githubusercontent.com/4485129/113470168-1b969200-9471-11eb-8618-51f587c8c7ae.png)


3. Create a database

![image](https://user-images.githubusercontent.com/4485129/113470204-61535a80-9471-11eb-864c-d6b0e6a55335.png)

Connect to database
![image](https://user-images.githubusercontent.com/4485129/113470304-3ae1ef00-9472-11eb-866f-8833a425d5eb.png)


4. Run basic commands in the database
![image](https://user-images.githubusercontent.com/4485129/113470338-7d0b3080-9472-11eb-8c67-d8299db86503.png)

 
</details>

### Step 2 - Ingest Sample Data https://docs.microsoft.com/en-us/azure/data-explorer/web-query-data
<details>
1. Login to https://dataexplorer.azure.com/#

![image](https://user-images.githubusercontent.com/4485129/113470422-25b99000-9473-11eb-8370-102b667bbd5a.png)

2. Assign role to access cluster

![image](https://user-images.githubusercontent.com/4485129/113478199-f58ae500-94a4-11eb-917a-6046c61d4621.png)

3. Add cluter 
```
https://azurecapstone10.eastus.kusto.windows.net

```

![image](https://user-images.githubusercontent.com/4485129/113470449-687b6800-9473-11eb-88a4-46c5933dbdda.png)

![image](https://user-images.githubusercontent.com/4485129/113478070-169f0600-94a4-11eb-8ef1-8fe0a8db0972.png)


4. Create table and ingest data 
```
.create table StormEvents (StartTime: datetime, EndTime: datetime, EpisodeId: int, EventId: int, State: string, EventType: string, InjuriesDirect: int, InjuriesIndirect: int, DeathsDirect: int, DeathsIndirect: int, DamageProperty: int, DamageCrops: int, Source: string, BeginLocation: string, EndLocation: string, BeginLat: real, BeginLon: real, EndLat: real, EndLon: real, EpisodeNarrative: string, EventNarrative: string, StormSummary: dynamic)
```

![image](https://user-images.githubusercontent.com/4485129/113478109-5d8cfb80-94a4-11eb-8d57-a7f339366449.png)

5. Ingest Data 
```
.ingest into table StormEvents 'https://kustosamplefiles.blob.core.windows.net/samplefiles/StormEvents.csv?sv=2019-12-12&ss=b&srt=o&sp=r&se=2022-09-05T02:23:52Z&st=2020-09-04T18:23:52Z&spr=https&sig=VrOfQMT1gUrHltJ8uhjYcCequEcfhjyyMX%2FSc3xsCy4%3D' with (ignoreFirstRecord=true)
```

![image](https://user-images.githubusercontent.com/4485129/113478120-739abc00-94a4-11eb-8a51-e6ffe0971b40.png)


6. After ingestion completes, paste in the following query, select the query in the window, and select Run.

```
StormEvents
| sort by StartTime desc
| take 10
```

  ![image](https://user-images.githubusercontent.com/4485129/113478144-94631180-94a4-11eb-8197-833b67290c8e.png)

</details>  

### Step 3 - Web Query Data https://docs.microsoft.com/en-us/azure/data-explorer/web-query-data
<details>

1. Add help cluster
  * In the upper left of the application, select Add Cluster.
  * In the Add cluster dialog box, enter the URI https://help.kusto.windows.net, then select Add.
    ![image](https://user-images.githubusercontent.com/4485129/113478317-bf9a3080-94a5-11eb-9dc0-51ccae74a870.png)

  * In the left pane, you should now see the help cluster. Expand the Samples database and open the Tables folder to see the sample tables that you have access to.
    ![image](https://user-images.githubusercontent.com/4485129/113478364-0a1bad00-94a6-11eb-8837-4ebb6c102f32.png)

2. Get data from cluster
  ![image](https://user-images.githubusercontent.com/4485129/113478407-47803a80-94a6-11eb-9f56-f802b6a0c95e.png)


4. Format Query 
```
StormEvents | sort by StartTime desc 
| project StartTime, EndTime, State, EventType, DamageProperty, EpisodeNarrative | take 10
```

* ![image](https://user-images.githubusercontent.com/4485129/113478439-75657f00-94a6-11eb-8a07-cae64a65b120.png)

![image](https://user-images.githubusercontent.com/4485129/113478420-5d8dfb00-94a6-11eb-88c3-171b3ac50733.png)
![image](https://user-images.githubusercontent.com/4485129/113478473-98902e80-94a6-11eb-85e2-9cd8ebc5192e.png)

5.  Execute Query 
![image](https://user-images.githubusercontent.com/4485129/113478489-ae9def00-94a6-11eb-8dcd-3062c4a2f122.png)


6. Execute Second Query 
![image](https://user-images.githubusercontent.com/4485129/113478503-c5444600-94a6-11eb-8852-16a64a8d3804.png)


7.  Group Columns by result
![image](https://user-images.githubusercontent.com/4485129/113478561-3126ae80-94a7-11eb-97e7-7c8671308027.png)
![image](https://user-images.githubusercontent.com/4485129/113478569-3c79da00-94a7-11eb-9e67-83c4ededd138.png)
![image](https://user-images.githubusercontent.com/4485129/113478580-4d2a5000-94a7-11eb-9c09-8e06232830dd.png)
![image](https://user-images.githubusercontent.com/4485129/113478585-59161200-94a7-11eb-80c6-00863baa9c76.png)



</details>

#### Delete the data 

<details>
  
![image](https://user-images.githubusercontent.com/4485129/113478888-4c92b900-94a9-11eb-85a8-13600c347a75.png)
  
* Delete Resource Group 
![image](https://user-images.githubusercontent.com/4485129/113478951-9f6c7080-94a9-11eb-9e6c-65bdde3bf1a0.png)
  
![image](https://user-images.githubusercontent.com/4485129/113478964-b1e6aa00-94a9-11eb-8ffa-86da23d9e70a.png)

</details>

### Pricing
<details>
  
![image](https://user-images.githubusercontent.com/4485129/113479099-95973d00-94aa-11eb-9a2c-ac56f02f382b.png)

</details>
