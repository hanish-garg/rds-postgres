+++
title = "Create the DB instance"
date = 2020-04-22T23:10:28-05:00
weight = 30
+++


Open the [Amazon RDS  service console](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2)  
Click **Create database** to start the configuration process. 

{{% img "consoledb.png" "Console" %}}

In the **Choose a database** creation method section, ensure the **Standard Create** option is selected.
Next, in the **Engine options** section, choose the **MySQL** engine type, the **MySQL Community** edition and the **MySQL 5.7.24** version.

{{% img "dbengine.png" "Console" %}}

In the **Templates** section, select **Production**.

{{% img "templates.png" "Console" %}}

In the **Settings** section, set the **DB instance identifier** to `labstack-mysql`. Configure the name and password of the master database user, with the most elevated permissions in the database. We recommend to use the user name `masteruser` for consistency with subsequent labs and a password of your choosing. For simplicity ensure the check box **Auto generate a password** is **not checked**.

{{% img "dbsettings.png" "Console" %}}

In the **DB instance size** section, select **Memory Optimized classes**, and choose `r5.large` in the size drop-down. 

{{% img "dbsize.png" "Console" %}}

In the **Storage Section**, select **Provisioned IOPS** under **Storage Type**, and set **100** as **Allocated Storage**. Select **1000** under **Provisioned IOPS**. **Uncheck** the **Enable storage autoscaling** box. 

{{% img "dbstorage.png" "Console" %}}

In the **Availability and Durability** section, select **Do not create a standby instance** as Multi-AZ deployment option.

{{% img "az.png" "Console" %}}

In the **Connectivity** section, select the `labstack-vpc` as the **Virtual Private Cloud (VPC)** value.  

Next expand the **Additional connectivity configuration**. Select **labstack-dbsubnets-xxxxx** value for the **subnet group**. Choose **No** as the value for **Publicly accessible** option.  
Select **Choose Existing** for **VPC security group**, and `labstack-mysql-internal` as the **Existing VPC security groups** value. Leave Database port value as 3306.

{{% img "connectivity.png" "Console" %}}

In the **Database Authentication** section, select **Password and IAM database authentication**.

{{% img "dbauth.png" "Console" %}}

**Expand Additional Configuration**.   
Enter `mylab` as the **Initial database** name value. In the **Backup** section select **Enable automatic backups**, select **1 Day** as the **Backup retention period** value.  

{{% img "dbbackup.png" "Console" %}}

In the **Encryption** section, select **Enable encryption**.  
Check the **Enable Performance Insights** box under **Performance Insights** section.


{{% img "dbencryption.png" "Console" %}}

In the **Monitoring** section, check **Enable Enhanced Monitoring**, and change the **Granularity** to **1 second**. Next, check **Error Log** and **Slow Query** Log boxes in the **Log Export** section. Finally **uncheck** the **Enable deletion protection**, and click on **Create Database**.

{{% img "createdb.png" "Console" %}}