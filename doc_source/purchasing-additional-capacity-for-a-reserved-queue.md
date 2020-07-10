# Purchasing additional capacity for a reserved queue in AWS Elemental MediaConvert<a name="purchasing-additional-capacity-for-a-reserved-queue"></a>

If you want to increase the number of jobs that your reserved queue can process at once, you can purchase additional capacity for it\. To purchase additional capacity, you extend your existing commitment with a new 12\-month commitment for a larger number of RTS\. The new commitment begins when you purchase the additional capacity\. You can't decrease the number of RTS in your reserved queue\.

**To purchase additional capacity for a reserved queue**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar of the MediaConvert console, choose the Region where you created the reserved queue\.  
![\[Choose a Region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Queues**\.

1. On the **Queues** page, in the **Reserved queues** section, choose the option next to the name of the queue that you want to purchase additional capacity for\.

1. Choose **Actions**, **Purchase additional capacity**\.

1. On the **Purchase additional capacity** page, in the **Commitment to purchase additional capacity** section, specify the new total number of RTS for the queue\. This number includes both the original amount of RTS and the new additional capacity\.

1. Select the **I agree** check box to confirm your intention to make a 12\-month commitment\. AWS bills you monthly for the RTS\.
**Important**  
After you commit to your new pricing plan, you can’t cancel it or revert to your original plan\.

1. Choose **Purchase additional capacity**\.

1. On the **Purchase additional capacity** confirmation page, review the details of your new pricing plan, and then choose **Purchase**\.