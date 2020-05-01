+++
title = "Create an AWS Secrets Manager secret"
date = 2020-04-22T23:53:00-05:00
weight = 32
+++

Open the [AWS Secrets Manager service console](https://us-west-2.console.aws.amazon.com/secretsmanager/home?region=us-west-2).

{{% notice warning %}}
**Region Check**  
Ensure you are still working in the correct region, especially if you are following the links above to open the service console at the right screen.
{{% /notice %}}


Click **Store a new secret** to start the configuration process.


{{% img "secretscr.png" "Console" %}}

In the **Select secret type** section, choose **Credentials for RDS database**, then input the **User name** (should be `masteruser`) and **Password** that you provided when you created the DB cluster previously.
Next, in the **Select which RDS database this secret will access** section, choose the DB instance identifier you assigned to your instance (e.g. labstack-mysql). Click Next.

{{% img "secretetype.png" "Console" %}}

Name the secret `secretMysqlMasterUser` and provide a relevant description for the secret, then click Next.

{{% img "secretstr.png" "Console" %}}

Finally, in the **Configure automatic rotation** section, leave the option of **Disable automatic rotation** selected. In a production environment you will want to use database credentials that rotate automatically for additional security. Click **Next**.

{{% img "secretert.png" "Console" %}}

In the **Review** section you have the ability to check the configuration parameters for your secret, before it gets created. Additionally, you can retrieve sample code in popular programming languages, so you can easily retrieve secrets into your application. Click **Store** at the bottom of the screen.
Once created, identify the **ARN** of the newly created secret. This value will be needed in subsequent labs. In the list of **Secrets** in the console, click on the name of the newly created secret.

{{% img "secretes.png" "Console" %}}

In the detail view of the secret, note the value for **Secret ARN**. Write this down, you will need it later.

{{% img "secretarn.png" "Console" %}}



