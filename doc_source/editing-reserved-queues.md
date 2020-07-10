# Editing reserved queues in AWS Elemental MediaConvert<a name="editing-reserved-queues"></a>

When you edit a queue, you can change the following:
+ The description, which helps you identify it in the queue dashboard\.
+ The auto renew status of the queue's pricing plan for reserved transcode slots \(RTS\)\. For more information, see [How you pay for transcoding with reserved queues](about-reserved-queues.md#how-you-pay-for-reserved-queues)\.
+ The paused or active status of the queue\. Pausing the queue prevents the service from starting any more jobs until you reactivate the queue\.

**To edit a queue**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. If you are editing a queue other than the default queue, on the navigation bar of the AWS Elemental MediaConvert console, choose the Region where you created the queue\.

   The default queue is available in all Regions\. Other queues appear only in the Region where you create them\.  
![\[Choose an AWS Region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Queues**\.

1. On the **Queues** page, choose the name of the queue that you want to edit\.

1. On the queue’s page, choose the **Edit queue** button\.

1. On the **Edit queue** page, make the changes that you want for the queue\.

1. Choose **Save queue**\.