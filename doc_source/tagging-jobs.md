# Tagging AWS Elemental MediaConvert Jobs<a name="tagging-jobs"></a>

A *tag* is a label that you assign or that AWS assigns to an AWS resource\. Each tag consists of a *key* and a *value*\. For tags that you assign, you define the key and value\. For example, you might define the key as "stage" and the value as "test\." Tags help you to identify and organize your AWS resources\. Tags that you assign to AWS Elemental MediaConvert jobs appear in Amazon CloudWatch Events notifications, so that you can integrate your jobs into a larger AWS workflow\. For example, you might use AWS Step Functions and AWS Lambda to sort through your jobs and run different post\-processing scripts depending on the values of the job tags\.

You add tags to jobs in one of the following ways:
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

**Note**  
Tags on MediaConvert jobs function differently from tags on MediaConvert queues, job templates, and presets\. For information about tags on queues, job templates, and presets, see [Tagging Queues, Templates, and Presets](tagging-queues-templates-presets.md)\.  
This chapter applies only to the tags that you add to jobs\.

## AWS Elemental MediaConvert Job Tag Restrictions<a name="job-tagging-restrictions"></a>

The following basic restrictions apply to tags on jobs:
+ Maximum number of tags per job – 10\.
+ Maximum **Key** length – 128 Unicode characters\.
+ Maximum **Value** length – 256 Unicode characters\.
+ Valid values for **Key** and **Value** – Uppercase and lowercase Unicode letters in any language, numbers, space, and the following characters: \_ \. : / = \+ \- and @\.
+ Tag keys and values are case sensitive\.
+ Don't use the `aws:` prefix for either keys or values\. It's reserved for AWS use\.