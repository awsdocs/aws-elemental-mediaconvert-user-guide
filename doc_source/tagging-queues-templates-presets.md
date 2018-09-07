# Tagging AWS Elemental MediaConvert Queues, Job Templates, and Output Presets<a name="tagging-queues-templates-presets"></a>

A *tag* is a label that you assign or that AWS assigns to an AWS resource\. Each tag consists of a *key* and a *value*\. For tags that you assign, you define the key and value\. For example, you might define the key as "stage" and the value as "test\." Tags help you to identify and organize your AWS resources\. Tags that you assign to AWS Elemental MediaConvert queues, job templates, and presets are integrated with tags across AWS services\. For more information about how and why to use these tags, see the [AWS Tagging Strategies](https://aws.amazon.com/answers/account-management/aws-tagging-strategies/) post on the *AWS Answers* blog\. Two popular use cases for these tags are as follows:
+ You can use the AWS Resource Groups Tagging API to tag and group your MediaConvert resources with other tagged AWS resources\. For more information, see the [Resource Groups Tagging API Reference](https://docs.aws.amazon.com/resourcegroupstagging/latest/APIReference/Welcome.html)\.
+ You can activate these tags on the AWS Billing and Cost Management dashboard, and then set up a monthly cost allocation report\. For more information, see [Setting Up Resources for Cost Allocation Through Tagging](setting-up-resources-for-catt.md)\.

Some actions that are available to you with other AWS services are not currently available with MediaConvert\. This includes setting up resource\-based permissions policies through AWS Identity and Access Management \(IAM\) and working with tags on MediaConvert resources through the Tag Editor on the AWS Management Console\.

**Note**  
Tags on MediaConvert queues, job templates, and presets function differently from tags on MediaConvert jobs\. For information about tags on jobs, see [Tagging Jobs](tagging-jobs.md)\.  
The following topics apply only to the tags that you add to queues, job templates, and output presets\.

**Topics**
+ [Setting Up AWS Elemental MediaConvert Resources for Cost Allocation Through Tagging](setting-up-resources-for-catt.md)
+ [Adding Tags When You Create an AWS Elemental MediaConvert Resource](add-tags-on-create.md)
+ [Adding Tags to an Existing AWS Elemental MediaConvert Resource](add-tags-to-existing.md)
+ [Viewing Tags on an AWS Elemental MediaConvert Resource](view-tags-on-resource.md)
+ [Editing Tags on a Resource](edit-tags-on-resource.md)
+ [Removing Tags from an AWS Elemental MediaConvert Resource](remove-tags-from-resource.md)
+ [AWS Elemental MediaConvert Queue, Template, and Preset Tag Restrictions](resource-tagging-restrictions.md)