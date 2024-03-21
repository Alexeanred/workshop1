---
title : "Add trigger to combine function"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 4.3.1 </b> "
---

1. Access the combine function in Lambda initialized in step 2:
     + Select **Add trigger**.
![combinefunc](/images/4.s3/001-combine.png)
2. In the search bar:
     + Enter **S3**.
![combinefunc](/images/4.s3/002-combine.png)
3. In **Trigger configuration**:
     + Bucket: **translated-bucket-<your_id>**.
     + Event types: default: **All object create events**.
     + Tick: **I acknowledge that ...**.
     + Select the **Add** button.
![combinefunc](/images/4.s3/003-combine.png)

**You have successfully added a trigger to the function.**
