---
title : "Create workshop user "
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1.1 </b> "
---


#### Create workshop IAM user
1. Access the console:
  + Go to the search bar.
  + Type **IAM**.

![user](/images/2.prerequisite/001-user.png)

2. In page **IAM**.
  + Select item **user**.
  + Select button **Create user**.

![user](/images/2.prerequisite/002-user.png)

3. In Step 1:
  + Type user name: ```workshop-1-user```.
  + Check **Provide user access to the AWS Management Console**.
  + Choose user type: **I want to create an IAM user**.
  + Choose **custom password**: nhập password cho user đó.
  + Uncheck **Users must create a new password at next sign-in**.
  + Choose button **Next**.
![user](/images/2.prerequisite/003-user.png)

4. In Step 2, choose **Add user to group**.
  + Choose button **Next**.
![user](/images/2.prerequisite/004-user.png)

5. In Step 3, review information and choose button **Create user**.
![user](/images/2.prerequisite/005-user.png)
6. In Step 4, Copy the necessary information to log in to the user.
![user](/images/2.prerequisite/006-user.png)
**You have created the user for workshop 1, next is to create the workshop role.**