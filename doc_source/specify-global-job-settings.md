# Step 5: Specify global job settings<a name="specify-global-job-settings"></a>

Global job settings apply to every output that the job creates, as shown in the following illustration\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/Job_global-settings.png)

**To specify global job settings**

1. In the **Job** pane, in the **Job settings** section, choose **Settings**\.

1. For **IAM role**, choose an IAM role that has permissions to access the Amazon S3 buckets that hold your input and output files\. The IAM role must have a trusted relationship with AWS Elemental MediaConvert\. For information about creating this role, see [Step 3: Set up IAM permissions ](iam-role.md)\.

1. Optionally, specify job\-wide timecode settings in the **Timecode configuration** pane\.
**Note**  
If your job incorporates audio or captions provided in a separate file from your input, or if you use the graphic overlay \(image inserter\) feature, it is especially important to get these settings right\.  
There are three distinct groups of timecode settings\. Global job timecode configuration is one of those three\. For more information about the different sets of timecode settings and how AWS Elemental MediaConvert manages timecodes, see [Setting up timecodes](setting-up-timecode.md)\.

1. Optionally, specify values for the other job settings and enable global processors\. For more information about individual settings, choose the **Info** link next to each setting\.