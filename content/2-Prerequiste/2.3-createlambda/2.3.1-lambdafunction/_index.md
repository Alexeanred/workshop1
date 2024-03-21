---
title : "Create Lambda functions"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 2.3.1 </b> "
---

### Create lambda function
1. In the console, go to the search bar, enter **lambda**:
![lambdafunc](/images/2.prerequisite/031-lambda.png)
2. After entering the lambda, select the **Create function** button.
![lambdafunc](/images/2.prerequisite/032-lambda.png)
3. In **Create function**:
     + Select **Author from stratch**.
     + Enter function name: ```batchingFunction```.
     + Select Runtime: **Python 3.12**.
     + Select architecture: **_x86_64**.
     + Select the **Create function** button.
![lambdafunc](/images/2.prerequisite/033-lambda.png)
4. Do the same 3 steps above to create the following 3 functions:
     + ```batchingFunction```
     + ```translateFunction```
     + ```combineFunction```
![lambdafunc](/images/2.prerequisite/034-lambda.png)
**So, we have created the lambda functions, the next step is to create roles so that the lambda has access to other resources.**
