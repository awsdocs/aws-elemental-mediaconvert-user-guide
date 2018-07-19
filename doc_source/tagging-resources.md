# Tagging AWS Elemental MediaConvert Resources<a name="tagging-resources"></a>

A *tag* is a label that you or AWS assigns to an AWS resource\. Each tag consists of a *key* and a *value*\. For tags that you assign, you define the key and value\. For example, you might define the key as "stage" and the value as "test\." Tags help you to identify and organize your AWS resources\. 

With AWS Elemental MediaConvert, there are two types of tags that you can use:
+ Tags that you add to MediaConvert jobs\. 

  You add these to jobs through the MediaConvert console on the **Job settings** page, on the **Metadata** pane\. You can also add these tags through the MediaConvert API as part of your job settings JSON payload\. These tags are available only within the MediaConvert service\.

  MediaConvert **Metadata** tags appear in your Amazon CloudWatch Events notifications for your MediaConvert jobs\. You might use these tags when you integrate your MediaConvert jobs into a larger AWS workflow by creating the code yourself that sorts through your jobs and takes action on them based on values of the metadata tags\.
+ Tags that you add to MediaConvert queues, job templates, and output presets\.

   For more information about how and why to use these tags, see the [AWS Tagging Strategies](https://aws.amazon.com/answers/account-management/aws-tagging-strategies/) post on the *AWS Answers* blog\. You can use the AWS Resource Groups Tagging API to tag and group your MediaConvert resources with other tagged AWS resources\. For more information, see the [Resource Groups Tagging API Reference](https://docs.aws.amazon.com/resourcegroupstagging/latest/APIReference/Welcome.html)\.
**Note**  
There are actions that you can take with tags in other AWS services that are not currently available with AWS Elemental MediaConvert\. This includes cost allocation through tagging in the AWS Cost Explorer and the AWS Budgets console and working with tags on MediaConvert resources through the AWS Tag Editor console\.

The following topics apply to the tags you add to queues, job templates, and output presets\.

**Topics**
+ [What You Can Do with Tags on AWS Elemental MediaConvert Resources](access-options-tagris.md)
+ [AWS Tag Restrictions](resource-tagging-restrictions.md)
+ [Working with Tags for AWS Elemental MediaConvert Resources](resource-tagging-instructions.md)