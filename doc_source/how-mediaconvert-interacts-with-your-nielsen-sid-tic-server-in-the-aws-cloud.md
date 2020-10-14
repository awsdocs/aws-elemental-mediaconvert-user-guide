# How AWS Elemental MediaConvert interacts with your Nielsen SID/TIC server in the AWS Cloud<a name="how-mediaconvert-interacts-with-your-nielsen-sid-tic-server-in-the-aws-cloud"></a>

The following diagram shows, at a high level, how MediaConvert interacts with the other parts of the system\. There are four major parts of the system that you set up by following instructions from Nielsen:
+ Transfer your Nielsen metadata \.zip file\. MediaConvert writes this file to the Amazon S3 bucket that you create\. You provide this bucket URL for the setting **Metadata destination** \(`[metadataDestination](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-metadatadestination)`\) when you set up your job\.
**Note**  
This bucket is different from the one that you set up for the media asset outputs of your job\. For information about that bucket, see [Step 2: Create storage for files](set-up-file-locations.md), which is a sub\-topic of the Getting started chapter of this guide\.
+ Set up an Amazon EC2 instance and an AWS Lambda proxy in an Amazon VPC\. Then install the SID/TIC server software and licence from Nielsen\.
+ Use Amazon API Gateway to set up a gateway to manage requests and responses between MediaConvert and your Nielsen SID/TIC server\.

  This should result in a REST endpoint that you provide for the setting **TIC server REST endpoint** \(`[ticServerUrl](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-ticserverurl)`\) when you set up your job\.
+ Use AWS Identity and Access Management \(IAM\) to manage access and authentication between MediaConvert, your API gateway, and your SID/TIC server\.
**Note**  
The roles and access you set up for this data sharing is different from the IAM permissions you set up to allow MediaConvert to access your input and output Amazon S3 buckets\. For information about that setup, see [Step 3: Set up IAM permissions ](iam-role.md), which is a sub\-topic of the Getting started chapter of this guide\.

![\[The video is rotated so that the top of the pre-rotation image is parallel to the right edge of the post-rotation video frame. Black vertical bars on the right and left accommodate the difference between the aspect ratio of the original video and the rotated video.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/NielsenWatermarking.png)