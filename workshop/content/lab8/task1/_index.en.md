+++
title = "Create a user and attach the required IAM policy"
date = 2020-04-25T23:58:14-04:00
weight = 80
chapter = false
pre = "<b>1. </b>"
+++

Open the [IAM service console](https://console.aws.amazon.com/iam/home?region=us-west-2#/home)  
Click **Users** to open the users page.
{{% img "IAM-users.png" "Console" %}}


Click **Add user** to open the users page.
{{% img "IAM-addusers.png" "Console" %}}

Enter any user name (For example - mike), select **Programmatic access**, **AWS Management console access**, provide a **custom password** and unselect **user must create a new password** option. 
Click **Next:Permissions** to go to next screen
{{% img "IAM-adduser.png" "Console" %}}

Click **Attach existing policies directly**. This opens a new tab to create a new policy.
{{% img "IAM-attachpolicy.png" "Console" %}}

Click **Create policy**
{{% img "IAM-createpolicy.png" "Console" %}}

Click **JSON**
{{% img "IAM-createpolicyjson.png" "Console" %}}

Create the policy in below format
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": "rds-db:connect",
            "Resource": "arn:aws:rds-db:us-west-2:xxxaccountidxxx:dbuser:db-xxxxxxxxxxxxxxxx/mike"
        }
    ]
}
```

Format of Resource field 
```
arn:aws:rds-db:us-west-2:xxxaccountidxxx:dbuser:db-xxxxxxxxxxxxxxxx/mike 
```
is as per below 
{{% img "iam-resourcedocumentation.png" "Console" %}}

To get DbiResourceId click **labstackmysql** in **RDS Database Service console**
{{% img "iam-dbconfig.png" "Console" %}}

Click **Configuration**
{{% img "iam-dbconfigvalue.png" "Console" %}}

Select **AccountID** and **ResourceID** and form the **Resource Field** for IAM policy
{{% img "iam-dbconfigvalueresourceidarn.png" "Console" %}}

Paste the Policy in **JSON** tab and Click **Review policy** 
{{% img "IAM-reviewpolicy.png" "Console" %}}

Name the policy as **iamconnectmike**

Click **Refresh** on the Add user **IAM Management Console** tab.
{{% img "iam-ref.png" "Console" %}}

Enter **iamconnect** in FilterPolicy textbox and you should see the newly created policy
{{% img "iam-iamconnectmike.png" "Console" %}}

Click **Next:Tags**
{{% img "iam-usertags.png" "Console" %}}

Click **Next:Review**
{{% img "iam-adduserreview.png" "Console" %}}

Click **Create user**
{{% img "iam-addusercreateuser.png" "Console" %}}

After user is created, you will see the **Access key ID** and Click **Show** to see **Secret access key**.
{{% img "iam-showkeys.png" "Console" %}}

As keys are available only in this screen and you won't be able to get access to them after this screen, please save the keys for future use
{{% img "iam-savekeys.png" "Console" %}}

Click **Close**

