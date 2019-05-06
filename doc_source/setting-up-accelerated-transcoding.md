# Setting Up Accelerated Transcoding in AWS Elemental MediaConvert<a name="setting-up-accelerated-transcoding"></a>

You set up accelerated transcoding for your AWS Elemental MediaConvert jobs in the same way that you set up unaccelerated jobs, except that you enable acceleration\.

**Note**  
We recommend that you use a dedicated transcoding queue for your accelerated transcoding jobs, to provide isolation between the resources that you use for your accelerated jobs and your other jobs\.

**To set up your transcoding job with accelerated transcoding \(console\)**

1. Set up your transcoding job as usual\. For more information, see [Setting Up a Job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

   Make sure that your job input files and output settings conform to the limitations and requirements listed in [Job Limitations for Accelerated Transcoding in AWS Elemental MediaConvert](job-requirements.md)\.

1. Change your timecode settings from the default value **Embedded** to **Start at zero**\.

   1. On the **Create job** page, in the **Job** pane on the left, under **Job settings**, choose **Settings**\.

   1. In the **Timecode configuration** pane, for **Source**, choose **Start at 0**\.

   1. On the **Create job** page, in the **Job** pane on the left, under **Inputs**, choose the input\.

   1. In the **Video selector ** pane, for **Timecode source**, choose **Start at 0**\.

1. If you don't already have a dedicated queue for accelerated transcoding jobs, create one\. For more information, see [Creating an On\-Demand Queue in AWS Elemental MediaConvert](creating-queues.md)\.\.

1. On the **Create job** page, in the **Job** pane on the left, in the **Job Settings** section, choose **Settings**\.

1. For **Acceleration**, choose **Enabled**\.

If you use the API or an SDK, you can find this setting in the JSON file of your job, called [AccelerationSettings](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-job-accelerationsettings)\.