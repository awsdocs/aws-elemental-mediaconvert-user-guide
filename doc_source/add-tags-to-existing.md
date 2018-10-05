# Adding Tags to an Existing AWS Elemental MediaConvert Resource<a name="add-tags-to-existing"></a>

The following procedure shows you how to add tags to existing queues, job templates, and output presets using the AWS Elemental MediaConvert console\. 

**Note**  
These AWS tags on AWS Elemental MediaConvert queues, job templates, and output presets are different from the tags that you can add to MediaConvert jobs\. For information about tags on jobs, see [Tagging Jobs](tagging-jobs.md)\.

For information about adding tags using the API, see the `POST` method in the [Tags](https://docs.aws.amazon.com/mediaconvert/latest/apireference/tags.html) endpoint section of the *MediaConvert API Reference*\.

**Note**  
Tags on your MediaConvert queues, job templates, and output presets don't appear in the JSON response to a `GET` request on the resource\. Instead, send a `GET` request to the `Tags` endpoint\.

**To add tags to queues, job templates, and output presets \(console\)**

1. Sign in to the AWS Management Console and open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Output presets**, **Job templates**, or **Queues**\.

1. Choose the name of the specific resource that you want to add a tag to\.

1. Choose the **Update**, **Edit queue**, or **Update preset** button in the upper right\. 

1. In the **Tags** section at the bottom of the page, choose **Add**\.

1. For **Tag key**, enter a name for the tag\. For **Tag value**, enter a value for the tag\.

1. Choose **Save**\.