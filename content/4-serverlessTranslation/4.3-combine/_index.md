---
title : "Combine process"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---

![architecture-serverless](/images/arc-clean.png)

### Overview
+ The combine process takes place finally to combine the translated files in the **translated bucket** into 1 file like the original file.
+ Receive events that already have translated files, the combine function will process, combine the files into 1 file and return the **Final Translated bucket**.

### Content
+ [Add trigger](4.3.1-trigger/)
+ [Function configuration](4.3.2-function/)