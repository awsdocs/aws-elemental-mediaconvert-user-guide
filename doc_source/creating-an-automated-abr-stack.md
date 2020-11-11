# Creating an automated ABR stack<a name="creating-an-automated-abr-stack"></a>

When you know whether you want to specify values for the optional limits, use one of the following procedures to set up automated ABR in your job\. For more information about these optional settings, see [How automated ABR works](how-automated-abr-works.md)\.

**To set up automated ABR \(console\)**

1. Begin setting up your job as usual\. For more information, see [Getting started with AWS Elemental MediaConvert](getting-started.md)\.

   Instead of following the general instructions for setting up output groups and outputs, follow this procedure\.

1. Enable accelerated transcoding\. This is optional, but we strongly recommend it\. For more information, see [Using accelerated transcoding](accelerated-transcoding.md)\.

1. On the **Create job** page, in the **Job** pane on the left, next to **Output groups**, choose **Add**\.

1. Choose a streaming output group type: Apple HLS, DASH ISO, Microsoft Smooth Streaming, or CMAF\.

1. Below the **Group settings** section, enable **Automated ABR**\.

1. For the settings in the **Automated ABR** section, optionally specify values\. These are the settings that specify limits that relate to the whole ABR stack\. If you choose to keep the default values, you should get good results\.

   For more information, see [How automated ABR works](how-automated-abr-works.md)\.

1. From the **Job** pane on the left, just below your output group, choose **Automated ABR base output**\. 

1. On the right, in the **Base encoding settings for auto\-generated ABR renditions** section, optionally specify values for the limits that relate to properties of the renditions in the stack\.  If you choose to keep the default values, you should get good results\.

   For more information, see [How automated ABR works](how-automated-abr-works.md)\.

1. Optionally, specify values for encoding settings that aren't directly related to automated ABR, such as codec profile and level\. Values you specify apply to all renditions in the stack\. If you choose to keep the default values, you should get good results\.

   For information about each individual setting, choose the **Info** link next to the setting in the console to view the setting description\.

1. If a default **Audio 1** tab is present in the **Base encoding settings for auto\-generated ABR renditions** section, remove it\.

   1. Choose the **Audio 1** tab\.

   1. Choose **Remove audio** in the upper right of the **Base encoding settings for auto\-generated ABR renditions** section\.

1. Optionally, add audio renditions\. Follow these steps for each audio rendition that you want in your ABR stack\.

   1. From the **Job** pane on the left, choose your output group\.

   1. In the **Outputs** section, choose **Add output with captions or audio** to add a new output\.

      **Output 1** holds your automated ABR video settings and represents every video rendition in your stack\.

   1. Choose the new output from the list of outputs\.

   1. In the **Encoding settings** section, set up your audio rendition as you would for a job that doesn't use automated ABR\. For more information, see [Creating audio ABR streaming outputs](audio-abr-streaming-outputs.md)\.

1. Optionally, add captions\. Do this as you would for a manually specified ABR stack\. For more information, see [Setting up captions in AWS Elemental MediaConvert jobs](including-captions.md)\.

1. Optionally, repeat this procedure to create additional ABR packages in different formats\. In a job that includes an automated ABR output group, all ABR output groups must use automated ABR\.

**To set up automated ABR \(API, CLI, or SDK\)**

If you use the API, CLI, or an SDK, specify the relevant settings in your JSON job specification and then submit it programmatically with your job\. For more information about submitting your job programmatically, see one of the introductory topics of the *AWS Elemental MediaConvert API Reference*:
+ [Getting started with AWS Elemental MediaConvert using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html)
+ [Getting started with AWS Elemental MediaConvert using the API](https://docs.aws.amazon.com/mediaconvert/latest/apireference/getting-started.html)

1. Determine the values that you want to set for automated ABR\. If you keep all the defaults, you should get good results\. For more information, see [How automated ABR works](how-automated-abr-works.md)\.

1. Use the MediaConvert console to generate your JSON job specification\. We recommend this approach, because the console functions as an interactive validator against the MediaConvert job schema\. Follow these steps to generate your JSON job specification using the console:

   1. Follow the previous procedure for the console\.

   1. In the **Job** pane on the left, under **Job settings**, choose **Show job JSON**\.

**Information for manually editing your JSON job specification**  
Find additional information, including where each setting belongs in the job settings structure, in the *AWS Elemental MediaConvert API Reference*\. Links in this list go to information about the setting in that document:

**Important**  
If you set up automated ABR by manually editing your JSON job specification, rather than exporting it from the console, you must explicitly set `qualityTuningLevel` to `MULTI_PASS_HQ` and `rateControlMode` to `QVBR`\.
+ Explicitly set these required settings:
  + Set `qualityTuningLevel` to `MULTI_PASS_HQ`\.
    + AVC \(H\.264\): `[qualityTuningLevel](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h264settings-qualitytuninglevel) in the H264Settings properties table`
    + HEVC \(H\.265\): `[qualityTuningLevel](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h265settings-qualitytuninglevel) in the H265Settings properties table`
  + Set `rateControlMode` to `QVBR`\.

    When you enable automated ABR, the usual required settings for QVBR, such as `qvbrSettings` and `qvbrQualityLevel`, aren't required\. Instead specify the required automated ABR settings\.
    + AVC \(H\.264\): `[rateControlMode](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h264settings-ratecontrolmode) in the H264Settings properties table`
    + HEVC \(H\.265\): `[rateControlMode](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h265settings-ratecontrolmode) in the H265Settings properties table`
+ Set the accelerated transcoding [mode](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-model-accelerationsettings) to `PREFERRED` or `ENABLED`\. This is optional, but we strongly recommend it\.
+ Optionally, specify thses limits that relate to the whole ABR stack:
  + **Automated ABR** : `[abrSettings](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-automatedencodingsettings-abrsettings)`
    + **Max renditions**: `[maxRenditions](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-automatedabrsettings-maxrenditions)` in the AutomatedAbrSettings properties table
    + **Max ABR bitrate**: `[maxAbrBitrate](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-automatedabrsettings-maxabrbitrate)` in the AutomatedAbrSettings properties table
    + **Min ABR bitrate**: `[minAbrBitrate](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-automatedabrsettings-minabrbitrate)` in the AutomatedAbrSettings properties table
+ Optionally, specify these limits that relate to properties of the renditions in the stack:
**Note**  
The API properties that correspond to these console settings function differently depending on whether they are in outputs that are part of an automated ABR stack\.
  + **Max resolution**: `[width](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-videodescription-width)` and `[height](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-videodescription-height)`
    + In automated ABR: Use these settings together to represent the maximum possible resolution in the ABR stack\.
    + In other outputs: Use these settings together to represent the output resolution\.
  + **Max frame rate**: `frameratecontrol`, `numerator`, and `denominator`

    For information about how these properties work and links to them in the API Reference, see [Frame rate conversion procedures; API, CLI, or SDK](converting-frame-rate.md#frame-rate-conversion-procedure-api)\.
    + In automated ABR: Use these settings to specify the frame rate of the highest\-bandwidth rendition in your stack\. If you don't specify these settings, MediaConvert uses the frame rate of your input video\.
    + In other outputs: Use these settings to specify the output frame rate\.