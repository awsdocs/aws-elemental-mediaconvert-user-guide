# Setting up a Dolby Vision job<a name="setting-up-a-dolby-vision-job"></a>

You can use AWS Elemental MediaConvert to create profile 5 Dolby Vision outputs\.

**To set up a Dolby Vision job**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create job**\.

1. For your input file or files, choose an MXF file or an IMF package that has frame\-interleaved Dolby Vision metadata\. 

   If your input is an IMF package, specify a CPL file for your input\. If your CPL is from an incomplete IMP, choose **Supplemental IMPs** to specify the location of your supplemental IMPs\.

1. Set up your input audio and video as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\. Make sure to keep the input color space set to the default value **Follow**\.

   Find the input color space setting as follows: On the **Create job** page, in the **Job** pane on the left, choose the input\. In the **Video selector** section on the right, find **Color space**\.

1. Set up your output groups, outputs, and video output selectors as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring complex jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\. 

1. For each output that you want processed with Dolby Vision, do the following:
   + Make sure that your output settings conform to the limitations listed in [Dolby Vision Job Limitations and Requirements](dolby-vision-job-limitations-and-requirements.md)\.
   + Enable the **Dolby Vision** preprocessor: 

     On the **Create job** page, in the **Job** pane on the left, choose the output\. At the bottom of the **Encoding settings** section on the right, choose **Dolby Vision**\.

1. Choose an on\-demand queue\. Your default queue is on\-demand\.

   Find the **Queue** setting as follows: On the **Create job** page, in the **Job** pane on the left, choose **Settings**\. In the **Job settings** section on the right, find **Queue**\.