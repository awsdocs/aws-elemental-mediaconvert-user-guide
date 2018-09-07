# Removing Tags from an AWS Elemental MediaConvert Resource<a name="remove-tags-from-resource"></a>

The following procedure shows you how to remove tags from existing queues, job templates, and output presets using the AWS Elemental MediaConvert console\.

To do this using the API, see the `PUT` method in the [Tags](https://docs.aws.amazon.com/mediaconvert/latest/apireference/tags.html) endpoint section of the *MediaConvert API Reference*\.

**Note**  
These AWS tags on AWS Elemental MediaConvert queues, job templates, and output presets are different from the tags you can add to MediaConvert jobs\. For information about tags on jobs, see [Tagging Jobs](tagging-jobs.md)

**To remove tags from a queue, job template, or output preset \(console\)**

1. Sign in to the AWS Management Console and open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Output presets**, **Job templates**, or **Queues**\.

1. Choose the name of the specific resource that has tags that you want to change\.

1. Choose the **Update**, **Edit queue**, or **Update preset** button in the upper right\. 

1. Next to any tag that you want to delete, choose **Remove**\.

1. Choose **Save**\.