---
title : "Create S3 buckets for batch translation"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 2.2.1 </b> "
---

### Create S3 bucket for input
1. On the console, go to the search bar, enter **S3** to access Amazon S3:
![batchS3](/images/2.prerequisite/020-batch.png)
2. In S3, select the **Create bucket** button to create a new bucket:
![batchS3](/images/2.prerequisite/021-batch.png)
3. In Create Bucket:
   + Select AWS Region: **Singapore (ap-southeast-1)**.
   + Enter bucket name: ```translate-job-batch-input-<your_id>```. For example: translate-job-batch-input-150903.
{{% notice tip %}}
Choose your own id so it doesn't overlap with the names of other buckets on Amazon S3.
{{% /notice %}}
![batchS3](/images/2.prerequisite/022-batch.png)
4. Leave other parameters as default, select **Create Bucket** button.
![batchS3](/images/2.prerequisite/023-batch.png)
5. After the bucket is successfully created, access the bucket.
   + Then, select the **Create folder** button.
![batchS3](/images/2.prerequisite/024-batch.png)
6. In Create folder:
   + Enter folder name: ```raw```.
   + Then, select the **Create folder** button.
![batchS3](/images/2.prerequisite/025-batch.png)

### Create S3 bucket for output
1. In S3, select the **Create bucket** button to create a new bucket:
![batchS3](/images/2.prerequisite/026-batch.png)
2. In Create Bucket:
   + Select AWS Region: **Singapore (ap-southeast-1)**.
   + Enter bucket name: ```translate-job-batch-output-<your_id>```. For example: translate-job-batch-output-150903.
{{% notice tip %}}
Choose your own id so it doesn't overlap with the names of other buckets on Amazon S3.
{{% /notice %}}
![batchS3](/images/2.prerequisite/027-batch.png)
3. Leave other parameters as default, select **Create Bucket** button.
![batchS3](/images/2.prerequisite/028-batch.png)
4. After the bucket is successfully created, access the bucket.
   + Then, select the **Create folder** button.
![batchS3](/images/2.prerequisite/029-batch.png)
5. In Create folder:
   + Enter folder name: ```output```.
   + Then, select the **Create folder** button.
![batchS3](/images/2.prerequisite/030-batch.png)

**You have finished creating 2 buckets for batch translation**.