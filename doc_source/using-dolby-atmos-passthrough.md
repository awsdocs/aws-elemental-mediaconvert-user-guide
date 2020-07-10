# Using Dolby Atmos passthrough with AWS Elemental MediaConvert<a name="using-dolby-atmos-passthrough"></a>

AWS Elemental MediaConvert can create Dolby Digital Plus with Atmos outputs by either encoding audio in 9\.1\.6 PCM mono channels, or by passing through already encoded Dolby Digital Plus with Atmos content\.

You set up your job to pass through Dolby Digital Plus with Atmos content in the same way that you pass through Dolby Digital and Dolby Digital Plus content\.

**To set up a Dolby Atmos job, passing through finished audio content**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create job**\.

1. Set up your input audio and video as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. Set up your output groups, outputs, and video output selectors as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring complex jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\. Choose supported containers as listed in [Supported output codecs and containers](reference-codecs-containers.md)\.

1. Create audio output selectors as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring complex jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\.

   Set them up as follows:

   1. In the **Job** pane on the left, choose an output that includes audio\.

   1. In the **Encoding settings** section, choose **Audio 1**\.

   1. For **Audio codec**, choose **Passthrough**\.

## Feature Restrictions for Dolby Atmos Passthrough<a name="feature-restrictions-for-dolby-atmos-passthrough"></a>

Note the following restrictions in the AWS Elemental MediaConvert implementation of Dolby Atmos passthrough:
+ **Output codec:** You can create Dolby Atmos audio outputs encoded with only the Dolby Digital Plus \(EAC3\) codec\.
+ **Output containers:** For file outputs, you can create Dolby Atmos audio in only one of the video containers that supports Dolby Digital Plus: MPEG\-4, MPEG\-2 Transport Stream, or QuickTime\.