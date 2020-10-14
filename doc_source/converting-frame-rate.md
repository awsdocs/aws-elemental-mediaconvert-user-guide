# Converting the frame rate of your video<a name="converting-frame-rate"></a>

 After you know how you want to specify the relevant settings, use one of the following procedures to set up your job\. For conceptual information and guidance about choosing the right values for these settings, see [Settings for frame rate conversion](settings-for-frame-rate-conversion.md)\.

**Topics**
+ [Frame rate conversion procedure, console](#frame-rate-conversion-procedure-console)
+ [Frame rate conversion procedures; API, CLI, or SDK](#frame-rate-conversion-procedure-api)

## Frame rate conversion procedure, console<a name="frame-rate-conversion-procedure-console"></a>

**To set up your transcoding job with frame rate conversion \(console\)**

1. Determine the values that you want to set for frame rate conversion\. For more information, see [Settings for frame rate conversion](settings-for-frame-rate-conversion.md)\.

1. Set up your job inputs and outputs as described in [Setting up a job](setting-up-a-job.md)\.

1. On the **Create job** page, in the **Job** pane on the left, choose the output that you want to use frame rate conversion with\.
**Tip**  
To find a specific encoding setting on the console, use your browser's search function\.

1. In the **Encoding settings** section, for **Frame rate**, choose the frame rate that you want for your output\. If the frame rate that you want isn't listed, choose **Custom**\. Then specify your frame rate as a fraction in the fields to the right of **Frame rate**\.

1. For **Framerate conversion algorithm**, choose the algorithm most suited to your content\.

   Note that **Framerate conversion algorithm** isn't available on the console until you choose your output frame rate\.

1. Optional\. If your output is 25 fps and you want to use **Slow PAL**, enable it\.

1. Optional\. If you're converting from 23\.976 fps to 29\.97 fps and you want to do a telecine conversion, set **Telecine** to **Hard** or **Soft**\.

   Note that **Telecine** isn't available on the console until you set your output frame rate to 29\.97\.

## Frame rate conversion procedures; API, CLI, or SDK<a name="frame-rate-conversion-procedure-api"></a>

If you use the API, CLI, or an SDK, specify the relevant settings in your JSON job specification and then submit it programmatically with your job\. For more information about submitting your job programmatically, see one of the introductory topics of the *AWS Elemental MediaConvert API Reference*:
+ [Getting started with AWS Elemental MediaConvert using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html)
+ [Getting started with AWS Elemental MediaConvert using the API](https://docs.aws.amazon.com/mediaconvert/latest/apireference/getting-started.html)

**To set up your transcoding job with frame rate conversion \(API, CLI, or SDK\)**

1. Determine the values you want to set for frame rate conversion\. For more information, see [Settings for frame rate conversion](settings-for-frame-rate-conversion.md)\.

1. Use the MediaConvert console to generate your JSON job specification\. We recommend this approach, because the console functions as an interactive validator against the MediaConvert job schema\. Follow these steps to generate your JSON job specification using the console:

   1. Follow the previous procedure for the console\.

   1. In the **Job** pane on the left, under **Job settings**, choose **Show job JSON**\.

Find additional information, including where each setting belongs in the job settings structure, in the *AWS Elemental MediaConvert API Reference*\. Links in this list go to information about the setting in that document:
+ **Frame rate control** \(`framerateControl`\)

  Use the frame rate control setting to specify whether MediaConvert uses the frame rate of your input sources or the frame rate that you specify with the `framerateNumerator` and `framerateDenominator` settings\.
**Note**  
The default behavior for this setting is to follow source\. Therefore, if you leave this setting out of your JSON job specification, MediaConvert ignores any values you provide for `framerateNumerator` and `framerateDenominator`\.
  + AV1: `[framerateControl](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-model-av1frameratecontrol)`
  + AVC \(H\.264\): `[framerateControl](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h264settings-frameratecontrol)`
  + HEVC \(H\.265\): `[framerateControl](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h265settings-frameratecontrol)`
  + MPEG\-2: `[framerateControl](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-mpeg2settings-frameratecontrol)`
  + Apple ProRes: `[framerateControl](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-proressettings-frameratecontrol)`
  + VP8: `[framerateControl](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-vp8settings-frameratecontrol)`
  + VP9: `[framerateControl](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-vp9settings-frameratecontrol)`
+ **Frame rate** \(`framerateNumerator` and `framerateDenominator`\)

  In the MediaConvert job settings schema, frame rate is represented as a fraction, to retain precision with irrational numbers\. Therefore, specify your frame rate value as `framerateNumerator` divided by `framerateDenominator`\. For values for common frame rates, see the table following this list of settings\.

  Links to `framerateNumerator`
  + AV1: `[framerateNumerator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-av1settings-frameratenumerator)`
  + AVC \(H\.264\): `[framerateNumerator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h264settings-frameratenumerator)`
  + HEVC \(H\.265\): `[framerateNumerator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h265settings-frameratenumerator)`
  + MPEG\-2: `[framerateNumerator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-mpeg2settings-frameratenumerator)`
  + Apple ProRes: `[framerateNumerator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-proressettings-frameratenumerator)`
  + VP8: `[framerateNumerator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-vp8settings-frameratenumerator)`
  + VP9: `[framerateNumerator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-vp9settings-frameratenumerator)`

  Links to `framerateDenominator`
  + AV1: `[framerateDenominator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-av1settings-frameratedenominator)`
  + AVC \(H\.264\): `[framerateDenominator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h264settings-frameratedenominator)`
  + HEVC \(H\.265\): `[framerateDenominator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h265settings-frameratedenominator)`
  + MPEG\-2: `[framerateDenominator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-mpeg2settings-frameratedenominator)`
  + Apple ProRes: `[framerateDenominator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-proressettings-frameratedenominator)`
  + VP8: `[framerateDenominator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-vp9settings-frameratedenominator)`
  + VP9: `[framerateDenominator](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-av1settings-frameratenumerator)`
+ **Frame rate conversion algorithm** \(`framerateConversionAlgorithm`\)
  + AV1: `[framerateConversionAlgorithm](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-av1settings-framerateconversionalgorithm)`
  + AVC \(H\.264\): `[framerateConversionAlgorithm](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h264settings-framerateconversionalgorithm)`
  + HEVC \(H\.265\): `[framerateConversionAlgorithm](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h265settings-framerateconversionalgorithm)`
  + MPEG\-2: `[framerateConversionAlgorithm](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-mpeg2settings-framerateconversionalgorithm)`
  + Apple ProRes: `[framerateConversionAlgorithm](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-vp8settings-framerateconversionalgorithm)`
  + VP8: `[framerateConversionAlgorithm](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-vp9settings-framerateconversionalgorithm)`
  + VP9: `[framerateConversionAlgorithm](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-av1settings-frameratedenominator)`
+ **Slow PAL** \(`slowPal`\)
  + AVC \(H\.264\): `[slowPal](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h264settings-slowpal)`
  + HEVC \(H\.265\): `[slowPal](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-mpeg2settings-slowpal)`
  + MPEG\-2: `[slowPal](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h264settings-slowpal)`
  + Apple ProRes: `[slowPal](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h264settings-slowpal)`
+ **Telecine** \(`telecine`\)
  + AVC \(H\.264\): `[telecine](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h264settings-telecine)`
  + HEVC \(H\.265\): `[telecine](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-h265settings-telecine)`
  + MPEG\-2: `[telecine](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-mpeg2settings-telecine)`
  + Apple ProRes: `[telecine](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-proressettings-telecine)`
  + **Scan type** \(`[InputScanType](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-input-inputscantype)`\)


**Common frame rate ratios**  

| Frame rate common name | Value for framerateNumerator | Value for framerateDenominator | 
| --- | --- | --- | 
| 23\.976 | 24,000 | 1,001 | 
| 29\.97 | 30,000 | 1,001 | 
| 59\.94 | 60,000 | 1,001 | 