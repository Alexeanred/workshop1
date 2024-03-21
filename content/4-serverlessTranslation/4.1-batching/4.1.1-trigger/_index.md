---
title : "Add trigger to batching function"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1.1 </b> "
---
1. Access the batching function in Lambda initialized in step 2:
     + Select **Add trigger**.
![batchingfunc](/images/4.s3/001-batching.png)
2. In the search bar:
     + Enter **S3**.
![batchingfunc](/images/4.s3/002-batching.png)
3. In **Trigger configuration**:
     + Bucket: **batching-bucket-<your_id>**.
     + Event types: default: **All object create events**.
     + Tick: **I acknowledge that ...**.
     + Select the **Add** button.
![batchingfunc](/images/4.s3/003-batching.png)

**You have successfully added a trigger to the function.**