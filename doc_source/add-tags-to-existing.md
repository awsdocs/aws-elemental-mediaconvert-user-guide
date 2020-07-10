# Adding tags to an existing AWS Elemental MediaConvert resource<a name="add-tags-to-existing"></a>

The following procedure shows you how to add tags to existing job templates, output presets, or queues using the AWS Elemental MediaConvert console\. You can add tags to jobs only when creating them\.

For information about adding tags using the API, see the `POST` method in the [Tags](https://docs.aws.amazon.com/mediaconvert/latest/apireference/tags.html) endpoint section of the *MediaConvert API Reference*\.

**Note**  
Tags on your MediaConvert resources don't appear in the JSON response to a `GET` request on the resource\. Instead, send a `GET` request to the `Tags` endpoint\. If you send your request directly to the API, rather than using an SDK, you must URL encode the resource ARN\.

**To add tags to job templates, output presets, and queues \(console\)**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Job templates**, **Output presets**, or **Queues**\.

1. Choose the name of the specific resource that you want to add a tag to\.

1. Choose the **Update**, **Edit queue**, or **Update preset** button in the upper right\. 

1. In the **Tags** section at the bottom of the page, choose **Add**\.

1. For **Tag key**, enter a name for the tag\. For **Tag value**, enter a value for the tag\.

1. Choose **Save**\.