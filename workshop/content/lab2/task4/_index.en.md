+++
title = "Configure the client workstation"
date = 2020-04-22T23:53:00-05:00
weight = 33
+++

Subsequent labs on this site use a consistent way to access DB credentials. To simplify interactions, the lab credentials are saved in environment variables on the client workstation you use to issue commands to the database. 
If you are not already connected to the Session Manager workstation command line, please connect following these instructions. Once connected, run the command below, replacing the [`secretArn`] placeholder with the ARN of the secret created above:

```
CREDS=`aws secretsmanager get-secret-value --secret-id [secretArn] | jq -r '.SecretString'`
export DBUSER="`echo $CREDS | jq -r '.username'`"
export DBPASS="`echo $CREDS | jq -r '.password'`"
echo "export DBPASS=\"$DBPASS\"" >> /home/ubuntu/.bashrc
echo "export DBUSER=$DBUSER" >> /home/ubuntu/.bashrc
```