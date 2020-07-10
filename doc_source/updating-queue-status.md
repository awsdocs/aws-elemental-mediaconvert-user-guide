# Pausing and reactivating on\-demand queues in AWS Elemental MediaConvert<a name="updating-queue-status"></a>

When you pause a queue, AWS Elemental MediaConvert doesn't start processing any jobs in that queue\. MediaConvert finishes processing any job that is already running when you pause it\.

The following procedure explains how to pause and reactivate a queue using the console\.

**To pause or reactivate an on\-demand queue**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. If you are pausing or reactivating a queue other than the default queue, on the navigation bar of the AWS Elemental MediaConvert console, choose the Region where you created the queue\.

   The default queue is available in all Regions\. Other queues appear only in the Region where you create them\.  
![\[Choose a Region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Queues**\.

1. On the **Queues** page, choose the name of the queue that you want to pause or reactivate\.

1. On the queue’s page, choose the **Edit queue** button\.

1. On the **Edit queue** page, for **Status**, choose **Paused** or **Active**\.

1. Choose **Save queue**\.