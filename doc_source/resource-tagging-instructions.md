# Working with Tags for AWS Elemental MediaConvert Resources<a name="resource-tagging-instructions"></a>

The following procedures show you how to use tags for your AWS Elemental MediaConvert queues, job templates, and output presets\.

**Note**  
AWS also adds system tags to your resources\. The following topics apply to user\-defined tags, not to system tags\.

**Topics**
+ [Add tags when you create a resource \(console\)](#add-tags-on-create-console)
+ [Add tags when you create a resource (CLI, API)](#add-tags-on-create-api-cli)
+ [List tags on existing resources (CLI)](#list-tags-cli)
+ [List tags on existing resources (API)](#list-tags-api)
+ [Add tags to an existing resource \(AWS CLI\)](#add-tags-existing-cli)
+ [Add tags to an existing resource (API)](#add-tags-existing-api)
+ [Remove tags from a resource (CLI)](#remove-tags-cli)
+ [Remove tags from a resource (API)](#remove-tags-api)<a name="add-tags-on-create-console"></a>

**To add tags when you create queues, job templates, and output presets \(MediaConvert console\)**Add tags when you create a resource \(console\)

When you create a queue, job template, or output preset, you can specify tags to include on that resource\.
**Note**  
Tags on your AWS Elemental MediaConvert resources don't appear on the MediaConvert console or in the JSON response to a `GET` request on the resource\.

1. Follow the steps in one of the following procedures to begin creating the resource, but don't save the resource:
   + [Creating a Queue](creating-queues.md)
   + [Creating a Custom Preset from Scratch](creating-template-from-scratch.md)
   + [Creating a Custom Preset from Scratch](creating-preset-from-scratch.md)
   + [Creating a Custom Preset from a System Preset](create-custom-preset-from-system-preset.md)

1. Find the **Tags** pane in the relevant location:
   + For queues, at the bottom of the **Create queue** page
   + For output presets, at the bottom of the **Create preset** page
   + For job templates, at the bottom of the **Create job** template page, after you choose **Settings** from the **Job** pane on the left

1. In the **Tags** pane, choose **Add**\.

1. Type values for **Tag key** and **Tag value**\.

1. Choose **Create** to save the new resource with its tags\.

**To add tags when you create queues, job templates, and output presets \(MediaConvert API and AWS CLI\)**  
When you create a resource using the AWS CLI, submit your JSON specification for the resource as usual\. Include resource tags as shown in the following JSON snippet\. The `tags` element is a top\-level element, a sibling to `name` and `description`:

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

**To list the tags for a queue, job template, or output preset \(AWS CLI\)**  
You can retrieve a list of all the tags on an AWS Elemental MediaConvert resource by sending a `list-tags-for-resource` command at the command line, as in the following example:

```
aws mediaconvert list-tags-for-resource --region us-east-1 --endpoint-url https://abcd1234.mediaconvert.us-east-1.amazonaws.com   --arn arn:aws:mediaconvert:us-east-1:111122223333:queues/BananaQueue
```

Replace the region name, account\-specific endpoint, and Amazon Resource Name \(ARN\) with your values:

```
aws mediaconvert list-tags-for-resource --region region-name-1 --endpoint-url https://abcd1234.mediaconvert.region-name-1.amazonaws.com   --arn arn:aws:mediaconvert:region-name-1:111122223333:resourcetype/resourcename
```

**Note**  
The region that you specify with the `--region` flag must match the region that is embedded in your account\-specific endpoint and the region of the resource, which is embedded in the ARN\.  
To get your account\-specific endpoint, send a `describe-endpoints` request to the public AWS Elemental MediaConvert endpoint for the region\. For more information, see [Getting Started with AWS Elemental MediaConvert Using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html)\.

**To list the tags for a queue, job template, or output preset \(MediaConvert API\)**  
You can retrieve a list of all the tags on an AWS Elemental MediaConvert resource by sending a `GET` request to the MediaConvert `ListTagsForResource` with the Amazon Resource Name \(ARN\) of the resource\. For more information, see [Tags arn](https://docs.aws.amazon.com/mediaconvert/latest/apireference/tags-arn.html) in the *MediaConvert API Reference*\.

**Tip**  
To simplify making API calls, copy and import the [AWS Elemental MediaConvert postman collection files](postman-collection-files.md)\.<a name="add-tags-existing-cli"></a>

**To add tags to existing queues, job templates, and output presets \(AWS CLI\)**Add tags to an existing resource \(AWS CLI\)

1. Get the Amazon Resource Name \(ARN\) of the resource that you want to add tags to by using one of these commands at the command line: `get-queue`, `get-job-template`, `get-preset`\. Use the `--name` flag to specify the resource, as in the following example:

   ```
   aws --endpoint-url=https://abcd1234.mediaconvert.us-east-1.amazonaws.com --region=us-east-1 mediaconvert get-queue --name="BananaQueue"
   ```

   If you don't have the name, you can find it in the console as described in the following procedures:
   + [Listing and Viewing Queues](listing-queues.md)
   + [Listing and Viewing Job Templates](listing-job-templates.md)
   + [Listing and Viewing Output Presets](listing-presets.md)

1. Send a `tag-resource` command with the ARN that you retrieved in the preceding step and the tags that you want to add, as in the following example:

   ```
   aws mediaconvert tag-resource --region us-east-1 --endpoint-url=https://abcd1234.mediaconvert.us-east-1.amazonaws.com --arn=arn:aws:mediaconvert:us-east-1:111122223333:presets/1080pMP4Preset --tags "Company=Banana"
   ```
**Note**  
The region that you specify with the `--region` flag must match the region that is embedded in your account\-specific endpoint and the region of the resource, which is embedded in the ARN\.  
To get your account\-specific endpoint, send a `describe-endpoints` request to the public AWS Elemental MediaConvert endpoint for the region\. For more information, see [Getting Started with AWS Elemental MediaConvert Using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html)\.

**To add tags to existing queues, job templates, and output presets \(MediaConvert API\)**  
You can add tags to an existing AWS Elemental MediaConvert resource by sending a `POST` request to the MediaConvert `tags` endpoint with the Amazon Resource Name \(ARN\) of the resource and the tags that you want to add\. For more information, see [Tags](https://docs.aws.amazon.com/mediaconvert/latest/apireference/tags.html) in the *MediaConvert API Reference*\.

**Tip**  
To simplify making API calls, copy and import the [AWS Elemental MediaConvert postman collection files](postman-collection-files.md)\.

**To remove tags from a queue, job template, or output preset \(AWS CLI\)**  
You can remove tags from an AWS Elemental MediaConvert resource by sending an `untag-resource` command at the command line with the Amazon Resource Name \(ARN\) of the resource and the keys of the tags that you want to remove, as in the following example:

```
aws mediaconvert untag-resource --region=us-east-1 --endpoint-url=https://abcd1234.mediaconvert.us-east-1.amazonaws.com --arn=arn:aws:mediaconvert:us-east-1:111122223333:presets/1080pMP4Preset --tag-keys "Company"
```

**Note**  
The region that you specify with the `--region` flag must match the region that is embedded in your account\-specific endpoint and the region of the resource, which is embedded in the ARN\.  
To get your account\-specific endpoint, send a `describe-endpoints` request to the public AWS Elemental MediaConvert endpoint for the region\. For more information, see [Getting Started with AWS Elemental MediaConvert Using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html)\.

**To remove tags from a queue, job template, or output preset \(MediaConvert API\)**  
You can remove tags from an AWS Elemental MediaConvert resource by sending a `DELETE` request to the MediaConvert `Tags` endpoint with the Amazon Resource Name \(ARN\) of the resource and the tags that you want to remove\. For more information, see [Tags](https://docs.aws.amazon.com/mediaconvert/latest/apireference/tags.html) in the *MediaConvert API Reference*\.

**Tip**  
To simplify making API calls, copy and import the [AWS Elemental MediaConvert postman collection files](postman-collection-files.md)\.