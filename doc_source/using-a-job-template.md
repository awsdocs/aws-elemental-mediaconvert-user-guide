# Using a job template to create a job in AWS Elemental MediaConvert<a name="using-a-job-template"></a>

Job templates apply to an entire transcoding job and provide values for settings that stay the same across multiple jobs\. You specify the input settings and the AWS Identity and Access Management \(IAM\) service role in the job itself\. These values are not saved in the template because they are likely to vary from job to job\.

**To create a job using a job template**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar of the MediaConvert console, choose the region where you want to create your job\. This is almost always the region where your input files are stored\.  
![\[Choose a region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Job templates**\.

1. In the **Job templates** pane, from the **Templates** dropdown list, choose **Custom job templates** or **System job templates**\.
**Note**  
Custom job templates appear only in the region where they are created\. When you choose **Custom job templates**, you see only the job templates created in the region you chose at the beginning of this procedure\.

1. Choose the name of the job template that you want to use\.

1. On the **Job template details** page, choose **Create job**\.

1. In the **Inputs** section of the **Job** pane, choose **Add**\.

1. Specify your input video, audio, and captions settings\.
**Note**  
Make sure that you specify your audio and captions selectors in a way that corresponds to the outputs that are specified in the job template\.

1. In the **Job settings** section of the **Job pane**, choose **Settings**\.

1. In the **Job settings** pane, in the **IAM role** dropdown list, choose the service role that you created to grant permissions to MediaConvert to access your resources on your behalf\. For instructions on creating this role, see [Getting started](getting-started.md)\.