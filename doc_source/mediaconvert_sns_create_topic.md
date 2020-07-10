# Step 1: Create a topic in Amazon SNS<a name="mediaconvert_sns_create_topic"></a>

The first part of setting up a CloudWatch Events rule is preparing the rule target\. In this case, that means creating and subscribing to an Amazon SNS topic\.

![\[The CloudWatch Events rule is represented by a rectangle that reads "Rule: Send me an email when one of my jobs has an error." Inside that rectangle are two rectangles, one representing the target and one representing the event source. In this image, the target rectangle is highlighted. It reads "Target, Amazon SNS Topic: Use my SNS topic that sends an email to the address I provide."\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/CloudWatchEvents_tutorial-target.png)

**To create an Amazon SNS topic**

1. Open the Amazon SNS console at [https://console\.aws\.amazon\.com/sns/v3/home](https://console.aws.amazon.com/sns/v3/home)\.

1. In the navigation pane, choose **Topics**, and then choose **Create new topic**\.

1. For **Topic name**, enter **MediaConvertJobErrorAlert**, and then choose **Create topic**\.

1. Choose the topic ARN link for the topic that you just created\. It looks something like this: **arn:aws:sns:region:123456789012:MediaConvertJobErrorAlert**\.

1. On the **Topic details: MediaConvertJobErrorAlert** page, in the **Subscriptions** section, choose **Create subscription**\. 

1. For **Protocol**, choose **Email**\. For **Endpoint**, enter the email address that you want Amazon SNS to send the notification to\.

1. Choose **Create subscription**\.

1. You will receive a notification email from Amazon SNS\. When you receive it, choose the **Confirm subscription** link in the email\. 