# Adding tags when you create an AWS Elemental MediaConvert resource<a name="add-tags-on-create"></a>

The following procedures show you how to add tags to your MediaConvert queues, job templates, and output presets when you create them\.

**Topics**

## Adding tags when creating a resource \(console\)<a name="add-tag-on-create-console"></a>

You can add tags when you create a queue, job template, or output preset\.

**To add tags when you create a queue, job template, or output preset \(console\)**

1. Follow the steps in one of the following procedures to begin creating the resource, but don't save the resource:
   + [Setting up a job](setting-up-a-job.md)
   + [Creating an on\-demand queue](creating-queues.md)
   + [Creating a custom preset from scratch](creating-template-from-scratch.md)
   + [Creating a custom preset from scratch](creating-preset-from-scratch.md)
   + [Creating a custom preset from a system preset](create-custom-preset-from-system-preset.md)

1. Find the **Tags** section in the relevant location:
   + For jobs – on the **Create job** page, after you choose **Settings** from the **Job** section on the left
   + For queues – at the bottom of the **Create queue** page
   + For output presets – at the bottom of the **Create preset** page
   + For job templates – at the bottom of the **Create job template** page, after you choose **Settings** from the **Job** section on the left

1. In the **Tags** section, choose **Add**\.

1. For **Tag key**, enter a name for the tag\. For **Tag value**, enter a value for the tag\.

1. Choose **Create** to save the new resource with its tags\.

## Adding tags when creating a resource \(API and AWS CLI\)<a name="add-tags-on-create-api"></a>

When you create a job, job template, output preset, or queue using the AWS Elemental MediaConvert API or the AWS CLI, submit your JSON specification for the resource as usual\. Include tags as shown in the following JSON example, in `tags`:

```
{
	"name": "Job Template Test with Resource Tags",
	"description": "Job Template Test",
	"tags":{
		"Company": "Banana",
		"Stage": "Production"		
	},
	"settings":{
```