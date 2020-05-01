+++
title = "Creating a lab environment using AWS CloudFormation"
date = 2020-04-20T22:52:43-05:00
weight = 6
+++

To simplify the getting started experience with the labs, we have created foundational templates for [AWS CloudFormation](https://aws.amazon.com/cloudformation/) that provision the resources needed for the lab environment. These templates are designed to deploy a consistent networking infrastructure, and client-side experience of software packages and components used in the lab.

{{% notice note %}}
**Formal Event**  
If you are running these labs in a formal instructional event, the lab environment may have been initialized on your behalf. If unsure, please verify with the event support staff.
{{% /notice %}}

Please use the template to initialize you environment by clicking on the **Launch Stack** button below. If you would like to look at the template, you can also download it.

| Launch Template | Download Template |
| ----- | ----- |
| <a href="https://console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/create/review?stackName=labstack&templateURL=https://s3.amazonaws.com/[[bucket]]/templates/lab-no-cluster.yml" target="_blank"><img src="../../en/lab1/task2/cloudformation-launch-stack.png?classes=shadow" alt="Launch Stack" style="float:left"></a> | [lab-template.yml](https://[[website]]/templates/lab-template.yml) |

{{% notice warning %}}

**Region Check**    
Ensure you are still working in the correct region, especially if you are following the link above to open the service console at the right screen.
{{% /notice %}}  

In the field named **Stack Name**, ensure the value `labstack` is preset. For the **Use AZs** parameter (Regional Settings section) select 3 availability zones (AZs) from the dropdown. If your desired region only supports 2 AZs, please select just the two AZs available.

{{% img "console-labstack.png" "Console" %}}  

Scroll to the bottom of the page, check the box that reads: **I acknowledge that AWS CloudFormation might create IAM resources with custom names** and then click **Create stack.**

{{% img "console-createstack.png" "Console" %}}

The stack will take approximatively 5 minutes to provision, you can monitor the status on the **Stack detail** page. You can monitor the progress of the stack creation process by refreshing the **Events** tab. The latest event in the list will indicate `CREATE_COMPLETE` for the stack resource.

{{% img "console-details.png" "Console" %}}

Once the status of the stack is `CREATE_COMPLETE`, click on the **Outputs** tab. The values here will be critical to the completion of the remainder of the lab. Please take a moment to save these values somewhere that you will have easy access to them during the remainder of the lab. The names that appear in the Key column are referenced directly in the instructions in subsequent steps, using the parameter format: `outputKey`

{{% img "outputs.png" "Console" %}}
