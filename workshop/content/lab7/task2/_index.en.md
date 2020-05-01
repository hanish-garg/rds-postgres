+++
title = "Creating, Modifying and Applying Options Groups"
date = 2020-04-26T14:09:24-04:00
weight = 75
chapter = false
pre = "<b>2. </b>"
+++

<div>Some DB engines offer additional features that make it easier to manage data and databases, and to provide additional security for your database. Amazon RDS uses option groups to enable and configure these features. An option group can specify features, called options, that are available for a particular Amazon RDS DB instance. Options can have settings that specify how the option works. When you associate a DB instance with an option group, the specified options and option settings are enabled for that DB instance.</div>


<div>Amazon RDS provides an empty default option group for each new DB instance. You cannot modify this default option group, but any new option group that you create derives its settings from the default option group. </div>


Open the [Amazon RDS  service console](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2)
Click **Databases** to view your databases. 
{{% img "Database.png" "Console" %}}

Click **labstack-mysql** to view your database instance
{{% img "labstack-mysql-db.png" "Console" %}} 

Click **Configuration** to view configuration inforamtion for your database instance
{{% img "Configurations.png" "Console" %}}

Scorll down in **Configuration** page and Click **Option groups**
{{% img "Option-groups.png" "Console" %}}

Shows properties of **Option group**
{{% img "OptionGroup-Values.png" "Console" %}}

You can view the **Option Groups** in the navigation pane as well
{{% img "OptionsGroupNav.png" "Console" %}}

Click **Create Option groups**
{{% img "CreateOptionGroup.png" "Console" %}}

Enter values in **Create Option group** window. Select **Name**, in **Name** box, enter description in **Description** box, select **mysql** as Engine and **5.7** as Major engine version. Click **Create**
{{% img "CreateOptionGroup-Values.png" "Console" %}}

New **Option Groups** is created
{{% img "NewOptionGroups.png" "Console" %}}

You can add an option to an existing option group. After you have added the options you want, you can then associate the option group with a DB instance so that the options become available on the DB instance.

{{% notice note %}}
Option group changes must be applied immediately in two cases:
When you add an option that adds or updates a port value, such as the OEM option.
When you add or remove an option group with an option that includes a port value.
In these cases, choose the Apply Immediately option in the console. 
{{% /notice %}}

To add option to new option group, Select **mysql-option-group** and Click **Add option**
{{% img "AddOptions.png" "Console" %}}

Choose **Option Name** from **MARIADB_AUDIT_PLUGIN** OR **MEMCACHED** and update required value. Select **Apply Immediately** and Click **Add Option**
{{% img "AddOption-Values.png" "Console" %}}

Options will show **MARIADB_AUDIT_PLUGIN**
{{% img "MARIA-DB-AUDIT-PLUGIN.png" "Console" %}}

To apply new **Option groups** to **labstack-mysql**, select **labstack-mysql** and Click **Modify**
{{% img "Modify-DB.png" "Console" %}}

Scroll down to **Database options** and select **mysql-option-group** from **Option group** dropdown
{{% img "NewOption-GroupDropdown.png" "Console" %}}

Scroll down to bottom of page and Click **Continue**
{{% img "Continues.png" "Console" %}}

Select **ApplyImmediately** and Click **Modify DB Instance**
{{% img "Apply-Immediately.png" "Console" %}}

After few minutes when Database is done **modifying** and shows **available** Click on database name 
{{% img "Availables.png" "Console" %}}

Click **Configuration** and scroll down to **Option groups** setting. New **Option Group** will be visible.
{{% img "Option-groups.png" "Console" %}}




