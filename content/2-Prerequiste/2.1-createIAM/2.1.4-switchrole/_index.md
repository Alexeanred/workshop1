---
title : "Access the user and change to the role for the workshop"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.1.4 </b> "
---

#### Access the user
1. In the upper right corner of your current account, select the **Sign Out** button.
![switch](/images/2.prerequisite/015-switch.png)
2. Enter the saved information of the workshop user to log in.
![switch](/images/2.prerequisite/016-switch.png)
3. After logging in, that account cannot do the workshop yet, we must switch Role.
#### Change to role for workshop

1. In the AWS management console:
   + Select user information in the upper right corner of the screen.
   + Select the **Switch role** button.
![switch](/images/2.prerequisite/017-switch.png)
2. Enter the necessary information:
   + Account: Enter **Account ID**
   + Role: Enter the Role name in that account. For example: workshop1-role.
   + Note: carefully check the role name is correct, otherwise the role will not be switched.
   + Display Name will automatically appear.
   + Choose a color to differentiate the Role.
   + Click the **Switch Role** button.
![switch](/images/2.prerequisite/018-switch.png)
3. After the Role Switch is successful, we will see the color of the Role on that user's information and try to access the services we are authorized to access.
![switch](/images/2.prerequisite/019-switch.png)
**We have completed setting up IAM for this workshop. We'll start with creating an S3 bucket.**