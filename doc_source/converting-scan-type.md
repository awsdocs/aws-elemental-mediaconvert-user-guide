# Converting the scan type of your video<a name="converting-scan-type"></a>

 After you know how you want to specify the relevant settings, use one of the following procedures to set up your job\. For conceptual information and guidance about choosing the right values for these settings, see [Settings for scan type conversion](settings-for-scan-type-conversion.md)\.

**To set up your transcoding job to convert scan type and telecine \(console\)**

1. Consult the topic [Settings for scan type conversion](settings-for-scan-type-conversion.md) to determine the values that you want to set for interlacing or deinterlacing\.

1. Set up your job inputs and outputs as described in [Setting up a job](setting-up-a-job.md)\.

1. On the **Create job** page, in the **Job** pane on the left, choose the output that you want to work with\.

1. Find the settings you need in the **Encoding settings** section as follows:
   + **Deinterlacer** preprocessor: Choose **Deinterlacer** from the list of preprocessors at the bottom of the **Encoding settings** section\.
   + **Deinterlace Control**: Find this setting in the **Deinterlacer** section after you enable the deinterlacer\.
   + **Deinterlace algorithm**: Find this setting in the **Deinterlacer** section after you enable the deinterlacer\.
   + **Deinterlace mode**: Find this setting in the **Deinterlacer** section after you enable the deinterlacer\.
   + **Interlace mode**: Find this setting directly under **Encoding settings**\. You might want to use your web browser's search function to find this setting\.
   + **Telecine**: This setting is only visible in the console when you set **Frame rate** to **29\.970**\. Find **Frame rate** directly under **Encoding settings**\. You might want to use your web browser's search function to find this setting\.

     The default value for **Telecine** is **None**\. Therefore, you only need to make this setting visible in the console when you are creating a telecine output\.

**To set up your transcoding job to convert scan type and telecine \(API, CLI, or SDK\)**

If you use the API, CLI, or an SDK, specify the relevant settings in your JSON job specification and then submit it programmatically with your job\. For more information about submitting your job programmatically, see one of the introductory topics of the *AWS Elemental MediaConvert API Reference*:
+ [Getting started with AWS Elemental MediaConvert using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html)
+ [Getting started with AWS Elemental MediaConvert using the API](https://docs.aws.amazon.com/mediaconvert/latest/apireference/getting-started.html)

1. Consult the topic [Settings for scan type conversion](settings-for-scan-type-conversion.md) to determine the values that you want to set for interlacing or deinterlacing\.

1. Use the MediaConvert console to generate your JSON job specification\. We recommend this approach, because the console functions as an interactive validator against the MediaConvert job schema\. Follow these steps to generate your JSON job specification using the console:

   1. Follow the previous procedure for the console\.

   1. In the **Job** pane on the left, under **Job settings**, choose **Show job JSON**\.

   Find additional information, including where each setting belongs in the job settings structure, in the *AWS Elemental MediaConvert API Reference*\. Links in this list go to information about the setting in that document:
   + **Deinterlacer** preprocessor: `[Deinterlacer](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-videopreprocessor-deinterlacer)`
   + **Deinterlace Control**: `[DeinterlacerControl](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-deinterlacer-control)`
   + **Deinterlace algorithm**: `[DeinterlaceAlgorithm](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-deinterlacer-algorithm)`
   + **Deinterlace mode**: `[DeinterlacerMode](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-deinterlacer-mode)`
   + **Interlace mode** \(`interlaceMode`\)
     + AVC \(H\.264\): `[interlaceMode](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h264settings-interlacemode)`
     + HEVC \(H\.265\): `[interlaceMode](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h265settings-interlacemode)`
     + MPEG\-2: `[interlaceMode](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-mpeg2settings-interlacemode)`
     + Apple ProRes: `[interlaceMode](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-proressettings-interlacemode)`
   + **Telecine** \(`telecine`\)
     + AVC \(H\.264\): `[telecine](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h264settings-telecine)`
     + HEVC \(H\.265\): `[telecine](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h265settings-telecine)`
     + MPEG\-2: `[telecine](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-mpeg2settings-telecine)`
     + Apple ProRes: `[telecine](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-proressettings-telecine)`
   + **Scan type** \(`[InputScanType](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-input-inputscantype)`\)