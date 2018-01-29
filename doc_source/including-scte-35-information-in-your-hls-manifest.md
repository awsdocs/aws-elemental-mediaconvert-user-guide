# Including SCTE\-35 Information in Your HLS Manifest<a name="including-scte-35-information-in-your-hls-manifest"></a>

For outputs in an HLS package, you can have the service include information in the HLS manifest about the SCTE\-35 markers that are in each of the outputs\.

**To include SCTE\-35 information in your HLS manifest:**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create new job**\.

1. Set up your input, output groups, and outputs for video and audio, as described in [Setting Up a Job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring Complex Jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\.

1. Under **Output groups**, choose **Apple HLS**\. 
**Note**  
Your outputs must be in an Apple HLS Output group if you want to include SCTE\-35 information in an HLS manifest\.

1. Choose **Advanced**\.

1. Under **Ad markers**, enable either **AWS Elemental**, **SCTE\-35 enhanced**, or both\. Use AWS Elemental ad markers if you plan to send use this output with other AWS Elemental media services\.