+++
title = "2. Modify the DB instance for Compute Scaling"
date = 2020-04-22T23:10:28-05:00
weight = 30
+++


Open the [Amazon RDS  service console](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2)  
Click **DB instances** to view the previously created DB instance.

{{% img "consoledb.png" "Console" %}}

Next, Click on **DB identifier** with the value `labstack-mysql` , You would see a similar page like below .Please note the **Class** of the instance at the moment is set to `db.r5.large`, Then click on **Modify**.
{{% img "databases_modify.png" "Database_modify" %}}


After clicking Modify, Please click on the arrow as shown below for **DB Instance class** to provide you a list of combination of instance classes / types to choose from, In the below screenshot, a **db.r5.xlarge** is selected to scale up compute
{{% img "databases_modify1.png" "Database_modify1" %}}


Then use the vertical scroll bar to scroll all the way to the bottom of that page, Click **CONTINUE**
{{% img "databases_modify2.png" "Database_modify2" %}}


You would see a page with **summary of modifications** like below, Then, select **Apply immediately** and click on **Modify DB Instance**
{{% img "databases_modify3.png" "Database_modify3" %}}


Now, Please note when you scroll the horizontal scroll bar to the right , You would see the value for the column with the name **status** set to `Modifying` , RDS is applying the new compute values to the instance. This would take couple of minutes or so.  Please use the **refresh icon** to refresh the value for status
{{% img "databases_modify4.png" "Database_modify4" %}}



Once the value for the column with the name **Status** changed to `Available`, You should see the value for the column with the name **Size** set to `db.r5.xlarge`
{{% img "databases_modify5.png" "Database_modify5" %}}
