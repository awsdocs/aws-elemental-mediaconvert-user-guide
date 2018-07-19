# Creating an AWS Elemental MediaConvert Job by Duplicating a Completed Job<a name="create-new-job-from-completed-job"></a>

To create a job that is similar to one that you ran before, you can duplicate a completed job from your job history, and then modify any settings that you need to change\.

**To create a job based on a completed job**

1. Sign in to the AWS Management Console and open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar of the AWS Elemental MediaConvert console, choose the region where the completed job was created\.

   Completed jobs appear only in the region where they are created\.  
![\[Choose a region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Jobs** to display the **Recent jobs** pane\.
**Tip**  
Optionally, from the **Status** dropdown list, choose **Complete** to filter your list of jobs to just those that finished successfully\.

1. On the **Recent jobs** pane, from the **Job ID** column of the job history, choose the job that you want to duplicate\.

1. On the **Job summary** page, choose the **Duplicate** button\.

1. Modify any settings that you want to be different in the new job\.

   For more information about each setting, choose the **Info** link located next to the setting or next to the heading for the group of settings\.
**Tip**  
Settings that are likely to change from job to job include the following: input file location, output destination locations, and output name modifiers\. If you are running transcoding jobs for customers of yours who have different AWS accounts from your account, you also must change the **IAM role** under **Job settings**\.

1. Choose the **Create** button at the bottom of the page\.