+++
title = "Connect to your workstation instance"
date = 2020-04-21T22:07:51-05:00
weight = 21
+++

Connect to your workstation instance
Open the [Systems Manager: Session Manager service console](https://us-west-2.console.aws.amazon.com/systems-manager/session-manager?region=us-west-2). Click **Configure Preferences**.

{{% notice warning %}}
**Region Check**  
Ensure you are still working in the correct region, especially if you are following the links above to open the service console at the right screen.
{{% /notice %}}

{{% notice info %}}
**Console Differences**  
The introduction screen with the **Configure Preferences** and **Start Session** buttons only appears when you start using Session Manager for the first time in a new account. Once you have started using this service the console will display the session listing view instead, and the preferences page is accessible by clicking on the **Preferences** tab. From there, click the **Edit** button if you wish to change settings.
{{% /notice %}}

{{% img "splash.png" "Console" %}}

Check the box next to **Enable Run As support for Linux instances**, and enter `ubuntu` in the text field. This will instruct Session Manager to connect to the workstation using the `ubuntu` operating system user account. Click **Save**.

{{% notice note %}}
You will only need to set the preferences once for the purposes of the labs. However, if you use Session Manager for other use cases you may need to revert the changes back as needed.
{{% /notice %}}

{{% img "ssm1.png" "SSM" %}}

Next, navigate to the **Sessions** tab, and click the **Start session** button.

{{% img "ssm2.png" "SSM" %}}

Select an EC2 instance to establish a session with. The workstation is named `labstack-bastion-host`, select it and click **Start session**.

{{% img "ssm3.png" "SSM" %}}

If you see a black command like terminal screen and a prompt, you are now connected to the workstation. Type the following commands to ensure a consistent experience, and that the connection is successful:

```markdown
bash
cd ~
```
