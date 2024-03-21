---
title : "Add trigger to translate function"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.2.1 </b> "
---

1. Access the translate function in Lambda initialized in step 2:
     + Select **Add trigger**.
![translatefunc](/images/4.s3/001-translate.png)
2. In the search bar:
     + Enter **S3**.
![translatefunc](/images/4.s3/002-translate.png)
3. In **Trigger configuration**:
     + Bucket: **batched-bucket-<your_id>**.
     + Event types: default: **All object create events**.
     + Tick: **I acknowledge that ...**.
     + Select the **Add** button.
![translatefunc](/images/4.s3/003-translate.png)

**You have successfully added a trigger to the function**


