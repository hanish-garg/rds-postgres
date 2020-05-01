+++
title = "3. Failover the DB by initiating a reboot"
date = 2020-04-22T23:10:28-05:00
weight = 30
+++


Open the [Amazon RDS  service console](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2)  
Click **DB instances** to view the previously created DB instance.

Select the radio button for the **DB identifier** with the value `labstack-mysql` , Then click on **Reboot**

{{% img "Failover1.png" "Failover1" %}}

On the following page, Ensure the box for **Reboot with Failover** is `checked`, And Click on **Reboot**

{{% img "Failover2.png" "Failover2" %}}

Go over to the Summary page of our database by clicking on **DB identifier** with the value `labstack-mysql`

{{% img "Failover3.png" "Failover3" %}}

Click on the **Logs & Events** to check the status of the failover

{{% img "Failover4.png" "Failover4" %}}

Now, Please go over to the **client workstation** where the while loop command is running on , You will notice there will be a change in the hostname in the mysql command output as shown below. You will also notice a brief notice of interruption right around the time of failover.

{{% img "Failover5.png" "Failover5" %}}
