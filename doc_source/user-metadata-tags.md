# Using metadata tags with AWS Elemental MediaConvert jobs<a name="user-metadata-tags"></a>

Unless you have existing integrations or workflows that rely on metadata \(`userMetadata`\) tags, we recommend that you use standard AWS tags for both automatic integration with AWS services and for custom integrations and workflows\. For more information, see [Tagging AWS Elemental MediaConvert resources](tagging-mediaconvert-resources.md)\.

A *tag* is a label that you assign or that AWS assigns to an AWS resource\. Each tag consists of a *key* and a *value*\. For tags that you assign, you define the key and value\. For example, you might define the key as "stage" and the value as "test\." Tags help you to identify and organize your AWS resources\. Metadata tags that you assign to AWS Elemental MediaConvert jobs appear in Amazon CloudWatch Events notifications\.

You add metadata tags to jobs in one of the following ways:
+ Through the MediaConvert console on the **Job settings** page, in the **Metadata** pane\. 
+ Through the MediaConvert API in your job settings JSON payload\. Include tags as shown in the following JSON snippet, in `userMetadata`\. For more information, see the [Jobs](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html) endpoint section of the *MediaConvert API Reference*\.

  ```
  {
  	"name": "Job Template Test with Resource Tags",
  	"description": "Job Template Test",
  	"userMetadata":{
  		"Company": "Banana",
  		"Stage": "Production"		
  	},
  	"settings":{
  ```

## AWS Elemental MediaConvert job tag restrictions<a name="job-tagging-restrictions"></a>

The following basic restrictions apply to tags on jobs:
+ Maximum number of tags per job – 10\.
+ Maximum **Key** length – 128 Unicode characters\.
+ Maximum **Value** length – 256 Unicode characters\.
+ Valid values for **Key** and **Value** – Uppercase and lowercase Unicode letters in any language, numbers, space, and the following characters: \_ \. : / = \+ \- and @\.
+ Tag keys and values are case sensitive\.
+ Don't use the `aws:` prefix for either keys or values\. It's reserved for AWS use\.