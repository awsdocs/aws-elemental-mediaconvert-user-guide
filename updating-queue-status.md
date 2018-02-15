# Pausing and Reactivating Queues in AWS Elemental MediaConvert<a name="updating-queue-status"></a>

If you want to cancel a job, we recommend that you first pause the corresponding queue so that AWS Elemental MediaConvert doesn't start processing the job\. After the status of a job changes from **Submitted** to **Progressing**, you can't cancel it\.

The following procedure explains how to pause and reactivate a queue by using the console\.

**To pause or reactivate a queue**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. In the navigation pane, choose **Queues**\.

1. Select the check box next to the queue that you want to pause or reactivate\.

1. Choose **Pause** or **Activate** as applicable\.