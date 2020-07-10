# Viewing tags on an AWS Elemental MediaConvert resource<a name="view-tags-on-resource"></a>

The following procedure shows you how to view tags on existing queues, job templates, and output presets using the AWS Elemental MediaConvert console\.

To do this using the API, see the `GET` method in the [Tags arn](https://docs.aws.amazon.com/mediaconvert/latest/apireference/tags-arn.html) endpoint section of the *MediaConvert API Reference*\. If you send your request directly to the API, rather than using an SDK, you must URL encode the resource ARN\.

**To view tags for queues, job templates, and output presets \(console\)**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Job templates**, **Output presets**, or **Queues**\.

1. Choose the name of the specific resource that has tags that you want to view\.

1. View the tags for the resource in the **Tags** section at the bottom of the page\.