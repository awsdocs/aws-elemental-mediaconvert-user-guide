# Creating a reserved queue in AWS Elemental MediaConvert<a name="creating-a-reserved-queue"></a>

Reserved queues allow you to purchase transcoding capacity for a 12\-month period, instead of paying per minute for each output\.

**To create a reserved queue**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\. 

1. On the navigation bar of the AWS Elemental MediaConvert console, choose the Region where you want to create the queue\.

   A default, on\-demand queue is available in all Regions\. Other queues appear only in the Region where you create them\.  
![\[Choose a Region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Queues**\.

1. On the **Queues** page, in the **Reserved queues** section, choose **Create reserved queue**\.

1. On the **Create reserved queue** page, in the **General information** section, enter a name and a description for the new queue\.

1. Optionally, use the **Reserved transcode slots \(RTS\) calculator** to help determine how many RTS you need\. Specify values as follows:
   + **Turnaround time** \- The time frame that you want your content transcoded in\. For example, if you need to finish transcoding three films each day, enter **24** for **hours** and **0** for **minutes**\.
   + **Number of jobs** \- The number of jobs that you want to complete within your turnaround time\. In the previous example, this value would be **3**\.
   + **Time to run one job** \- The amount of time that it takes to transcode a piece of content\. The time strongly depends on your transcoding settings\. The best way to determine a value for this setting is to run a typical job in an on\-demand queue, with **Simulate reserved queue** enabled\.

     Find this setting as follows: On the **Create job** page, in the **Job** pane on the left, under **Job settings**, choose **Settings**\. In the **Job settings** section on the right, for **Simulate reserved queue**, choose **Enabled**\.

1. In the **Commitment to purchase RTS for reserved queue** section, specify the number of reserved transcode slots \(RTS\) that you want to purchase\. A reserved queue can simultaneously process a number of jobs equal to the number of RTS that you purchase for it\.

1. Select the **I agree** check box to confirm your intention to make a 12\-month commitment\. AWS bills you monthly for the RTS\.
**Important**  
After you commit to your pricing plan, you can’t cancel it\.

1. Choose **Create reserved queue**\.

1. On the **Purchase RTS for reserved queue** confirmation page, review the details of your pricing plan, and then choose **Purchase**\.

   If you decide later that you want to purchase additional capacity for your reserved queue, you can do so\. For more information, see [Purchasing additional capacity for a reserved queue](purchasing-additional-capacity-for-a-reserved-queue.md)\.