+++
title = "Create the user in RDS and login to database"
date = 2020-04-26T04:38:54-04:00
weight = 82
chapter = false
pre = "<b>2. </b>"
+++

## Connect to the Session Manager Workstation

<div>To interact with the RDS MySQL database instance, you will use an Amazon EC2 Linux instance that acts like a workstation to interact with the AWS resources in the labs on this website. All necessary software packages and scripts have been installed and configured on this EC2 instance for you. To ensure a unified experience, you will be interacting with this workstation using AWS Systems Manager Session Manager. With Session Manager you can interact with your workstation directly from the management console, without the need to install any software on your own devices.</div>  



## This lab requires the following prerequisites:

* [Deploy Environment]({{< ref "/Lab1/_index.en.md" >}})
* [IAM User]({{< ref "/Lab8/task1/_index.en.md" >}})


Connect to your workstation instance. Open the [Systems Manager: Session Manager service console](https://us-west-2.console.aws.amazon.com/systems-manager/session-manager?region=us-west-2) by clicking this link or searching **Systems Manager** in AWS Console.
{{% img "systemsmaanger.png" "Console" %}}

Click **Sessions Manager**
{{% img "sessionsmanager.png" "Console" %}}


Click **Start session**
{{% img "Start-session.png" "Console" %}}

Select an EC2 instance to establish a session with. The workstation is named `labstack-bastion-host`, select it and click **Start session**.
{{% img "ssm3.png" "Console" %}}

If you see a black command like terminal screen and a prompt, you are now connected to the workstation. Type the following commands to ensure a consistent experience, and that the connection is successful:

```markdown
bash
cd ~
```

Subsequent labs on this site use a consistent way to access DB credentials. To simplify interactions, the lab credentials are saved in environment variables on the client workstation you use to issue commands to the database. 
```
RDSHOST=`aws rds describe-db-instances --db-instance-identifier labstack-mysql --query "DBInstances[*].Endpoint.Address" --output text`
ARN=`aws secretsmanager list-secrets | jq -r '.SecretList[0].ARN'`
CREDS=`aws secretsmanager get-secret-value --secret-id $ARN  | jq -r '.SecretString'`
export DBUSER="`echo $CREDS | jq -r '.username'`"
export DBPASS="`echo $CREDS | jq -r '.password'`"
echo "export DBPASS=\"$DBPASS\"" >> /home/ubuntu/.bashrc
echo "export DBUSER=$DBUSER" >> /home/ubuntu/.bashrc
```
Execute the following command to download the ssl certificate
```
wget https://s3.amazonaws.com/rds-downloads/rds-ca-2019-root.pem
```

Execute the following command to connect to database
```
mysql --host=$RDSHOST --port=3306 --ssl-ca=./rds-ca-2019-root.pem --enable-cleartext-plugin --user=$DBUSER --password=$DBPASS
```

Execute the following command to add new user to RDS

```
CREATE USER mike IDENTIFIED WITH AWSAuthenticationPlugin AS 'RDS'; 
```
{{% img "grantaccess.png" "Console" %}}

To verify the user is created, execute the following command

```
select user,host from mysql.user;
```
{{% img "mikeuser.png" "Console" %}}

type **exit** to exit out of database

```
exit
```
{{% img "exit.png" "Console" %}}

Generate ***authentication token*** for user mike to connect to database by executing the following command
```
TOKEN="$(aws rds generate-db-auth-token --hostname $RDSHOST --port 3306 --region us-east-2 --username mike)"
```
{{% img "authtoken.png" "Console" %}}

Connect to **RDS MYSQL** using username = **mike** and password as TOKEN
```
mysql --host=$RDSHOST --port=3306 --ssl-ca=./rds-ca-2019-root.pem --enable-cleartext-plugin --user=mike --password=$TOKEN

```

**Success login** without entering the password

{{% img "successlogin.png" "Console" %}}



