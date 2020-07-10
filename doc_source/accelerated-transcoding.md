# Using accelerated transcoding in AWS Elemental MediaConvert<a name="accelerated-transcoding"></a>

AWS Elemental MediaConvert jobs that create premium content, such as those that incorporate Ultra High Definition \(UHD\) and High Dynamic Range \(HDR\) content, can have high computational requirements and can take longer to complete\. To reduce the transcoding time required to run these jobs, you can use accelerated transcoding\. Consider using accelerated transcoding for jobs that would otherwise take 10 minutes or longer to run\.

For example, jobs that generate the following assets might benefit from accelerated transcoding:
+ Ultra High Definition content
+ High dynamic range content in HEVC
+ Any long\-duration, visually complex video

**Note**  
Accelerated transcoding is a Professional tier feature\. You pay more per minute of transcoded output for outputs that use Professional tier features\. For more information about MediaConvert pricing tiers, see [MediaConvert pricing](https://aws.amazon.com/mediaconvert/pricing/)\.

**Topics**
+ [Setting up accelerated transcoding in AWS Elemental MediaConvert](setting-up-accelerated-transcoding.md)
+ [Job limitations for accelerated transcoding in AWS Elemental MediaConvert](job-requirements.md)
+ [Example accelerated transcoding JSON job for AWS Elemental MediaConvert](sample-acceleration-job-settings-in-json.md)