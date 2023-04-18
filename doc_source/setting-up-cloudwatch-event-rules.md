# Setting up EventBridge rules<a name="setting-up-cloudwatch-event-rules"></a>

To set up Amazon EventBridge rules: Create a rule that links the event from AWS Elemental MediaConvert and the target service that responds to your job status change, such as Amazon Simple Notification Service \(Amazon SNS\) or AWS Lambda\. 

For a tutorial on setting up an EventBridge rule with AWS Elemental MediaConvert, see [Tutorial: Setting up email notifications for failed jobs](#mediaconvert_sns_tutorial)\.

For a list of the events that MediaConvert sends in the EventBridge event stream, see [List of MediaConvert EventBridge events](mediaconvert_event_list.md)\.

For more general information about using EventBridge, see the [Amazon EventBridge User Guide](https://docs.aws.amazon.com/eventbridge/latest/userguide/)\.

For troubleshooting information, see [Troubleshooting Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-troubleshooting.html) in the *Amazon EventBridge User Guide*\. 

**Topics**
+ [Tutorial: Setting up email notifications for failed jobs](#mediaconvert_sns_tutorial)
+ [Step 1: Create a topic in Amazon SNS](#mediaconvert_sns_create_topic)
+ [Step 2: Specify an event pattern in an EventBridge rule](#mediaconvert_sns_rule_event_source)
+ [Step 3: Add the Amazon SNS topic and finish your rule](#add-target-and-finish-rule)
+ [Step 4: Test your rule](#mediaconvert_sns_test_rule)

## Tutorial: Setting up email notifications for failed jobs<a name="mediaconvert_sns_tutorial"></a>

In this tutorial, you configure an EventBridge event rule that captures events when a job status changes to `ERROR` and then notifies you about the event\. To do this, you first create a topic in Amazon SNS that will send you an email notification about the failed job\. Next, you create a rule in EventBridge by defining an event source and referencing the Amazon SNS topic \(the "target"\)\.

## Step 1: Create a topic in Amazon SNS<a name="mediaconvert_sns_create_topic"></a>

The first part of setting up an EventBridge rule is preparing the rule target\. In this case, that means creating and subscribing to an Amazon SNS topic\.

**To create an Amazon SNS topic**

1. Open the Amazon SNS console at [https://console\.aws\.amazon\.com/sns/v3/home](https://console.aws.amazon.com/sns/v3/home)\.

1. In the navigation pane, choose **Topics**, and then choose **Create topic**\.

1. For **Type**, choose **Standard**\.

1. For **Name**, enter **MediaConvertJobErrorAlert**, and then choose **Create topic**\.

1. Choose the topic **Name** for the topic that you just created to view the **Topic details**\.

1. On the **MediaConvertJobErrorAlert** **Topic details** page, in the **Subscriptions** section, choose **Create subscription**\. 

1. For **Protocol**, choose **Email**\. For **Endpoint**, enter the email address that you want Amazon SNS to send the notification to\.

1. Choose **Create subscription**\.

1. You will receive a notification email from Amazon SNS\. When you receive it, choose the **Confirm subscription** link in the email\. 

## Step 2: Specify an event pattern in an EventBridge rule<a name="mediaconvert_sns_rule_event_source"></a>

This step shows how to specify your event pattern in an EventBridge rule\. This rule will capture events sent by MediaConvert when a job status changes to `ERROR`\. 

**To set up an event pattern in an EventBridge rule**

1. Open the Amazon EventBridge console at [https://console\.aws\.amazon\.com/events/](https://console.aws.amazon.com/events/)\.

1. In the navigation pane, choose **Rules**\. Keep the **default** **Event bus** and then choose **Create rule**\.

1. For **Name**, enter **MediaConvertJobStateError**, and then choose **Next**\.

1. In the **Event pattern** section, starting with **Event source** choose the following settings:
   + **Event source**: **AWS services**
   + **AWS service**: **MediaConvert**
   + **Event type**: **MediaConvert Job State Change**
   + **Event type, Specific state\(s\)**: **ERROR**

1. An **Event pattern** box will look like the following example\. 

   ```
   {
     "source": ["aws.mediaconvert"],
     "detail-type": ["MediaConvert Job State Change"],
     "detail": {
       "status": ["ERROR"]
     }
   }
   ```

   This code defines an EventBridge event rule that matches any event where the job status changes to `ERROR`\. For more information about event patterns, see [Events and event patterns](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CloudWatchEventsandEventPatterns.html) in the *Amazon CloudWatch User Guide*\.

1. Choose **Next**\.

## Step 3: Add the Amazon SNS topic and finish your rule<a name="add-target-and-finish-rule"></a>

Add the Amazon SNS topic that you created in step 1 to the EventBridge rule that you started in step 2\.

**To add the Amazon SNS topic and finish the EventBridge rule**

1. In the **Select target\(s\)** section, under **Select a target**, choose **SNS topic**\.

1. For **Topic**, choose **MediaConvertJobErrorAlert**\.

1. Choose **Next**\.

1. Optionally add tags\. Then choose **Next**\.

1. Review your settings\. Then choose **Create rule**\. 

## Step 4: Test your rule<a name="mediaconvert_sns_test_rule"></a>

To test your rule, submit a job that you know will cause an error\. For example, specify an input location that does not exist\. If you configured your event rule correctly, you should receive an email with the event text message in a few minutes\. 

**To test the rule**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Submit a new MediaConvert job\. For more information, see [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. Check the email account that you specified when you set up your Amazon SNS topic\. Confirm that you received an email notification for the job error\.