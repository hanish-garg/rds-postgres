+++
title = "3. Modifying the DB Instance size for Read Scaling"
date = 2020-04-22T23:10:28-05:00
weight = 30
+++


Open the [Amazon RDS  service console](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2)  
Click **DB instances** to view the previously created DB instance.

{{% img "consoledb.png" "Console" %}}

Next, Select the **DB identifier** with the value `labstack-mysql` ,  Then click on the **Actions** for a drop down list, In that list click on **Create read replica**. You would see a similar page like below
{{% img "databases_modify.png" "Database_modify" %}}


Then Choose the instance specifications that you want to use. We recommend that you use the same DB instance class and storage type as the source DB instance for the read replica. For **Multi-AZ deployment**, choose `Yes` to create a standby of your replica in another Availability Zone for failover support for the replica.

Creating your read replica as a Multi-AZ DB instance is independent of whether the source database is a Multi-AZ DB instance.
{{% img "databases_modify1.png" "Database_modify1" %}}


Now, Use the vertical scroll bar to scroll until you see the **Settings** Section. For **DB instance identifier**, enter a name for the read replica. ( For Ex: `labstack-mysql-reader` )
{{% img "databases_modify2.png" "Database_modify2" %}}


Then use the vertical scroll bar to scroll all the way to the bottom of that page, Click on **Create read replica**
{{% img "databases_modify3.png" "Database_modify3" %}}


Now, You would be seeing the Databases dashboard, Please note there is a new entry in the **DB Identifier** with the name `labstack-mysql-readreplica` with a **Role** of `Replica`,  **Status** of `Creating`.
{{% img "databases_modify4.png" "Database_modify4" %}}


Now, Please use the **refresh icon** to refresh the value for status until you see the **Status** for the replica is changed to `Available`
{{% img "databases_modify5.png" "Database_modify5" %}}
