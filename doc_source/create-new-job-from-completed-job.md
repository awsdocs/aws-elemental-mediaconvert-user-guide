# Creating an AWS Elemental MediaConvert job by duplicating a completed job<a name="create-new-job-from-completed-job"></a>

To create a job that is similar to one that you ran before, you can duplicate a completed job from your job history, and then modify any settings that you need to change\.

**To create a job based on a recently completed job**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar of the MediaConvert console, choose the Region where the completed job was created\.

   Completed jobs appear only in the Region where they are created\.  
![\[Choose a Region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Jobs** to display the **Jobs** page\.
**Tip**  
Optionally, from the **Status** dropdown list, choose **Complete** to filter your list of jobs to just those that finished successfully\.

1. On the **Jobs** page, from the **Job ID** column of the job history, choose the job that you want to duplicate\.

1. On the **Job summary** page, choose the **Duplicate** button\.

1. Modify any settings that you want to be different in the new job\.

   For more information about each setting, choose the **Info** link located next to the setting or next to the heading for the group of settings\.
**Tip**  
Settings that are likely to change from job to job include the following: input file location, output destination locations, and output name modifiers\. If you are running transcoding jobs for customers of yours who have different AWS accounts from your account, you also must change the **IAM role** under **Job settings**\.

1. Choose the **Create** button at the bottom of the page\.