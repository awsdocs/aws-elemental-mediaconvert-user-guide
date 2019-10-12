# Tagging AWS Elemental MediaConvert Resources<a name="tagging-mediaconvert-resources"></a>

A *tag* is a label that you assign or that AWS assigns to an AWS resource\. Each tag consists of a *key* and a *value*\. For tags that you assign, you define the key and value\. For example, you might define the key as "stage" and the value as "test\." Tags help you to identify and organize your AWS resources\. Tags that you assign to AWS Elemental MediaConvert jobs, job templates, queues, and presets are integrated with tags across AWS services\.

Popular use cases for these tags are as follows:
+ You can use the AWS Resource Groups Tagging API to tag and group your MediaConvert resources with other tagged AWS resources\. For more information, see the [Resource Groups Tagging API Reference](https://docs.aws.amazon.com/resourcegroupstagging/latest/APIReference/Welcome.html)\.
+ You can activate these tags on the AWS Billing and Cost Management dashboard, and then set up a monthly cost allocation report\. For more information, see [Setting Up Resources for Cost Allocation Through Tagging](setting-up-resources-for-catt.md)\.
+ You can allow or deny resource\-level access to your resources using AWS Identity and Access Management \(IAM\)\. For more information, see [Controlling Access to AWS Resources Using Resource Tags](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_tags.html) in the *IAM User Guide*\.

**Note**  
You can use two types of tags on your MediaConvert jobs: standard AWS tags \(`tags`\) and metadata tags \(`userMetadata`\)\. Standard AWS tags integrate with AWS Billing and Cost Management, the AWS Resource Groups Tagging API, and IAM resource\-based permissions\. Metadata tags aren't integrated with other AWS services\.  
Unless you have existing integrations or workflows that rely on metadata tags, we recommend that you use standard AWS tags for both automatic integration with AWS services and for custom integrations and workflows\.

The following topics apply only to standard AWS tags\.

**Topics**
+ [Setting Up AWS Elemental MediaConvert Resources for Cost Allocation Through Tagging](setting-up-resources-for-catt.md)
+ [Adding Tags When You Create an AWS Elemental MediaConvert Resource](add-tags-on-create.md)
+ [Adding Tags to an Existing AWS Elemental MediaConvert Resource](add-tags-to-existing.md)
+ [Viewing Tags on an AWS Elemental MediaConvert Resource](view-tags-on-resource.md)
+ [Editing Tags on a Resource](edit-tags-on-resource.md)
+ [Removing Tags from an AWS Elemental MediaConvert Resource](remove-tags-from-resource.md)
+ [AWS Elemental MediaConvert Queue, Template, and Preset Tag Restrictions](resource-tagging-restrictions.md)