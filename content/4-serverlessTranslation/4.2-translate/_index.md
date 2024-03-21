---
title : "Translate process"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2 </b> "
---


![architecture-serverless](/images/arc-clean.png)

### Overview
+ After receiving events, objects have been put into the **batched-bucket** bucket.
+ **Translation function** will send the text in those files to Amazon Translate for translation, then Amazon Translate's API will return the translated text.
+ Translated files are put into **Translated bucket**.

### Content
+ [Add trigger](4.2.1-trigger/)
+ [Function configuration](4.2.2-function/)