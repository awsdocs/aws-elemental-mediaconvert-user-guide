# How automated ABR works<a name="how-automated-abr-works"></a>

With all adaptive bitrate \(ABR\) streaming, the end viewer's player device adjusts which rendition of the package it downloads based on the available bandwidth\. For example, a viewer with access to high\-quality wifi would automatically see a high\-bitrate rendition\. When they move to a location with only limited bandwidth, their player device automatically switches over to a lower\-bitrate rendition\. How well the adaptive streaming works depends on the construction of the ABR stack and how well that construction suits the content of the specific video\. For example, with a fast\-moving, visually complex asset, your ABR stack might include two 720p outputs with different bitrates\. If you used that same stack setup with a simple cartoon, those two outputs would likely look the same\. The extra encoding, storage, and distribution would cost money without conferring any benefit to the end viewer\.

When you run an automated ABR job, MediaConvert maximizes the video quality that the end viewer sees based on their available bandwidth\. It does this by analyzing a broad set of possible renditions and eliminating any that increase required bandwidth without increasing video quality\. When you run your job, MediaConvert analyzes the content of your input video and chooses the number of renditions and the characteristics of each rendition for you\.

You can use the console to run your job without setting anything\. There are three categories of optional settings you can specify if you choose to:
+ Limits on your adaptive bitrate \(ABR\) stack\.
+ Limits that apply to the renditions in the ABR stack\. These output\-level limits apply to all renditions in the stack\.
+ All other encoding settings\.

  For these settings, MediaConvert uses default values unless you specify something different\. This works the same as with outputs that don't use automated ABR, except that whatever values you set apply to all renditions in the stack\. For example, if you set **Profile** to **High 10\-bit**, every rendition will have that codec profile\.

## Settings that apply to the ABR stack<a name="settings-that-apply-to-the-abr-stack"></a>

You can set the following limits that relate to the whole ABR stack:
+ **Max renditions**: This is the upper limit for the number of renditions in your ABR stack\. The number of renditions in your stack might be less than this, but won't be more\.

  You can specify a number from 3–15\. If you don't specify this, the default maximum is 15\.
+ **Max ABR bitrate**: This is the upper limit for the bitrate of the highest\-bitrate rendition in your stack\. If MediaConvert achieves the same video quality at this bitrate and at a lower bitrate, it will use that lower bitrate output for your highest\-quality rendition\.

  If you don't specify this, the default maximum is 8 mb/s\.
+ **Min ABR bitrate**: This is the lower limit on the bitrate of any rendition in your stack\. MediaConvert won't create a rendition with a lower bitrate than this value\.

  If you don't specify this, the default minimum is 600 kb/s\.

## Settings that apply to renditions in the stack<a name="settings-that-apply-to-renditions-in-the-stack"></a>

You can set the following limits that relate to properties of the renditions in the stack:
+ **Max resolution**: This is the maximum resolution of your highest\-bitrate rendition\. When you set this value, choose the resolution of the highest quality device that you expect end viewers to use\. MediaConvert won't create a rendition with a resolution larger than this\.

  If you don't specify this, the default maximum is the resolution of your input video\.

  If you specify a value larger than your input video's resolution, MediaConvert uses your input resolution as the maximum\. MediaConvert won't use a resolution larger than the input for any rendition because upscaling the input resolution would add bandwidth without adding video quality\.
+ **Max frame rate**: MediaConvert uses this value as the frame rate for the for highest\-bandwidth rendition in your stack\. Depending on the input, this might be the frame rate for all renditions\. When your input frame rate is high, MediaConvert might halve the frame rate for lower\-bandwidth renditions\. For example, if your input frame rate is 60 fps, MediaConvert might use 30 fps for some of the lower\-bandwidth renditions, and perhaps 15 fps for the very lowest\.

  If you don't specify this value, the default maximum is your input frame rate\. If your job has multiple inputs, MediaConvert uses the frame rate of the first\.

For these settings, MediaConvert determines these values for each rendition automatically:
+ **Quality tuning level**: MediaConvert encodes all renditions with **Multi pass HQ**\.

  This behavior is automatic in the console but not when you submit your job programmatically\. When you set up your JSON job specifcation without using the console, you must explicitly set `qualityTuningLevel` to `MULTI_PASS_HQ`\.
+ **Rate control mode**: MediaConvert encodes all renditions with [QVBR](cbr-vbr-qvbr.md) rate control mode\.

  This behavior is automatic in the console but not when you submit your job programmatically\. When you set up your JSON job specifcation without using the console, you must explicitly set `rateControlMode` to `QVBR`\.
+ These QVBR required settings:
  + **QVBR quality level**:
  + **Max bitrate**
  + **Max average bitrate**
+ **HDR buffer size**
+ **HDR buffer initial fill**