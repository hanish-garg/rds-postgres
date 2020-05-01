+++
title = "1. Modify the DB instance for Storage Scaling"
date = 2020-04-22T23:10:28-05:00
weight = 30
+++


Open the [Amazon RDS  service console](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2)  
Click **DB instances** to view the previously created DB instance.

{{% img "consoledb.png" "Console" %}}


Next, Click on **DB identifier** with the value `labstack-mysql` , You would see a similar page like below , Then click on **Modify**


{{% img "databases_modify.png" "Database_modify" %}}



After clicking Modify, Please change the value for **Allocated storage** from currently `100 GIB` to `200 GiB` , Also change the value for **Provisioned IOPS** from `1000` to `2000` for scaling the storage

{{% img "databases_modify1.png" "Database_modify1" %}}


Then use the vertical scroll bar to scroll all the way to the bottom of that page, Click **CONTINUE**
{{% img "databases_modify2.png" "Database_modify2" %}}



You would see a page with **summary of modifications** like below, Then, select **Apply immediately** and click on **Modify DB Instance**
{{% img "databases_modify3.png" "Database_modify3" %}}

Now, Please note when you scroll the horizontal scroll bar to the right , You would see the value for the column with the name **status** set to `Modifying` , RDS is applying the new storage values to the instance. This would take couple of minutes or so.  Please use the **refresh icon** to refresh the value for status
{{% img "databases_modify4.png" "Database_modify4" %}}


Once the value for the column with the name **Status** changed to `Available`, You should see the value for the column with the name **Storage** set to `200GiB`
{{% img "databases_modify5.png" "Database_modify5" %}}
