+++
title = "Verify DB Instance"
date = 2020-04-22T23:53:00-05:00
weight = 35
+++


Let's make sure your DB instance has been created properly. First let's ensure the credentials have been saved correctly in the environment variables, run:

```
echo $DBUSER
```
You should see `masteruser` as the response string. Next, verify the version of the database engine created. Run the command below, replacing the [`DBEndpont`] placeholder with the value of the DB endpoint created in the preceding steps:

```
mysql -h[DBEndpoint] -u$DBUSER -p"$DBPASS" -e"SELECT @@version;"

```
You should see a response containing version number `5.7.24`.

