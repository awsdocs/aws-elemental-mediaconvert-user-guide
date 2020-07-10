# Exporting and importing AWS Elemental MediaConvert jobs<a name="exporting-and-importing-jobs"></a>

Completed MediaConvert jobs remain on the **Jobs** page for three months\. If you want to be able to run a new job based on a completed job more than three months after you run it, export the job after it is complete and save it\. Depending on how many jobs that you run, exporting and then importing a job can be simpler than finding a particular job in your list and duplicating it\.

**To export a completed job**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar of the MediaConvert console, choose the Region where the job that you want to export was created\.

   Completed jobs appear only in the Region where they are created\.  
![\[Choose a Region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Jobs** to display the **Jobs** page\.
**Tip**  
Optionally, from the **Status** dropdown list, choose **Complete** to filter your list of jobs to just those that finished successfully\.

1. On the **Jobs** page, from the **Job ID** column of the job history, choose the job that you want to export\.

1. On the **Job summary** page, choose the **Export JSON** button\.

1. Choose a file location for your exported JSON job specification on the hard drive of the computer that you use to operate the MediaConvert console, and then save the file\.

**To create a job by importing a previously exported completed job**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar of the MediaConvert console, choose the Region where you want to create your new job\.

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Jobs** to display the **Jobs** page\.

1. On the **Jobs** page, choose the **Import job** button\.

1. Modify any settings that you want to be different in the new job\.

   For more information about each setting, choose the **Info** link located next to the setting or next to the heading for the group of settings\.
**Tip**  
Settings that are likely to change from job to job include the following: input file location, output destination locations, and output name modifiers\. If you run transcoding jobs for customers of yours who have different AWS accounts from your account, you also must change the **IAM role** under **Job settings**\.

1. Choose the **Create** button at the bottom of the page\.