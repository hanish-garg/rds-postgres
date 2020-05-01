+++
title = "Creating, Modifying and Applying a Parameter Group"
date = 2020-04-26T14:09:20-04:00
weight = 71
chapter = false
pre = "<b>1. </b>"
+++

Open the [Amazon RDS  service console](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2)
Click **Databases** to view your databases. 
{{% img "Database.png" "Console" %}}

Click **labstack-mysql** to view your database instance
{{% img "labstack-mysql-db.png" "Console" %}} 

Click **Configuration** to view configuration inforamtion for your database instance
{{% img "Configuration.png" "Console" %}}

Scorll down in **Configuration** page and Click **Parameter group**
{{% img "ParameterGroup.png" "Console" %}}

<div left-align>This shows list of parameters in this default **Parameter group**</div>
{{% img "ParameterGroupValues.png" "Console" %}}


You can view the **Parameter Groups** in the navigation pane as well
{{% img "ParameterGroupNav.png" "Console" %}}

Click **Create Parameter group**
{{% img "CreateParameterGroup.png" "Console" %}}

Enter values in **Create Parameter group** window. Select **DB Parameter group family**, in **Group name** box, enter name for parameter group, in **Description** box, enter description for the new DB parameter group. Click **Create**
{{% img "CreateParameterGroupValues.png" "Console" %}}

New **Parameter Group** is created
{{% img "NewParameterGroup.png" "Console" %}}

<div>You can modify parameter values in a customer-created DB parameter group; you can't change the parameter values in a default DB parameter group. Changes to parameters in a customer-created DB parameter group are applied to all DB instances that are associated with the DB parameter group. </div>

<div>Changes to some parameters are applied to the DB instance immediately without a reboot. Changes to other parameters are applied only after the DB instance is rebooted. The RDS console shows the status of the DB parameter group associated with a DB instance on the Configuration tab. For example, if the DB instance isn't using the latest changes to its associated DB parameter group, the RDS console shows the DB parameter group with a status of pending-reboot. To apply the latest parameter changes to that DB instance, manually reboot the DB instance.</div>

To modify the **Parameter Group** Click on **mysql-lab-parameter-group**
{{% img "NewParameterGroup.png" "Console" %}}

Select a parameter **binlog_cache_size** and Click **Edit pamaters**
{{% img "EditParameter.png" "Console" %}}

Enter the new value of **binlog_cache_size** and Click **Save Changes**
{{% img "EditParameterValue.png" "Console" %}}

New Value is updated
{{% img "NewValue.png" "Console" %}}

You can **Associate** new **Parameter group** to **labstack-mysql** database. Click **Databases** on left navigation pane and Click **labstack-mysql** to view your database instance 
{{% img "ConfigurationInfo.png" "Console" %}}

Click **Modify**
{{% img "Modify.png" "Console" %}}

Scroll down to **Database options** and select **mysql-lab-parameter-group** from **DB Parameter group** dropdown
{{% img "NewParameterGroupDropdown.png" "Console" %}}

Scroll down to bottom of page and Click **Continue**
{{% img "Continue.png" "Console" %}}

Select **ApplyImmediately** and Click **Modify DB Instance**
{{% img "ApplyImmediately.png" "Console" %}}

Click **Configuration** and scroll down to **Parameter group** setting. It shows **pending-reboot**
{{% img "pendingreboot.png" "Console" %}}



