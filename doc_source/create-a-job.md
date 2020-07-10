# Step 6: Create a job<a name="create-a-job"></a>

A job does the work of transcoding\. You specify the name of the file that you want to transcode \(the input file\), the name that you want MediaConvert to give the transcoded file, the preset that you want MediaConvert to use, and a few other settings\. MediaConvert gets the input file from the Amazon S3 location that you specify in your job input settings, transcodes the file, and saves the transcoded file or files in the output location that you specify in the settings of the job output group\.

**To create a job**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Get started**\.

1. Choose **Create job**\.

1. Provide transcode instructions and job settings\. For more information, see [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\. 

   Make sure that you pick the same Region for your job and your file storage\. 

1. Choose **Create**\.

   For information about tracking the status of your job, see [Using CloudWatch Events with AWS Elemental MediaConvert](cloudwatch_events.md)\.

   For information about the file names and paths for your job outputs, see [Output file names and paths](output-file-names-and-paths.md)\.

1. If you don't want to keep the transcoded files that you generate during this tutorial, delete them from Amazon S3 to avoid incurring storage charges\.