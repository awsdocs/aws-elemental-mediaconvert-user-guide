# Purchasing transcoding capacity for an existing reserved queue<a name="purchasing-a-new-contract-for-an-existing-reserved-queue"></a>

After your initial pricing plan term for reserved transcode slots \(RTS\) expires, your reserved queue persists without the capacity to run transcoding jobs\. You can send jobs to the queue, but AWS Elemental MediaConvert doesn't process them\. To begin processing jobs through the queue again, you can set up a new pricing plan, which requires a new 12\-month commitment\.

**To purchase transcoding capacity for an existing reserved queue**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar of the MediaConvert console, choose the Region where you created the reserved queue\.  
![\[Choose a Region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Queues**\.

1. On the **Queues** page, in the **Reserved queues** section, choose **Actions**, **Purchase additional capacity**\.

1. On the **Purchase additional capacity** page, in the **Commitment to purchase additional capacity** section, specify the total number of RTS for the queue\.

1. Select the **I agree** check box to confirm your intention to make a 12\-month commitment\. AWS bills you monthly for the RTS\.
**Important**  
After you commit to your pricing plan, you can’t cancel it\.

1. Choose **Purchase additional capacity**\.

1. On the **Purchase additional capacity** confirmation page, review the details of your pricing plan, and then choose **Purchase**\.