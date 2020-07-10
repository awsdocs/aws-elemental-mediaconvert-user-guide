# Converting the color space<a name="converting-the-color-space"></a>

If you want your output video to use a different color space than your input video, use color space conversion\. Set up color space conversion in the output **Color corrector** settings\.

**To convert the color space**

1. Confirm that MediaConvert supports the conversion that you want to do\. See [Supported color space conversions](hdr-support.md#supported-color-space-conversions)\.

1. Set up your transcoding job as usual\. For more information, see [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. On the **Create job** page, in the **Job** pane on the left, choose your HDR output\.

1. At the bottom of the **Encoding settings** section on the right, choose **Preprocessors**\.

1. Choose **Color corrector** to display the color correction settings\.

1. For **Color space conversion**, choose the color space that you want for your output\.

1. If you are converting to HDR 10, specify values for the **HDR master display information** settings\.

   These values don't affect the pixel values that are encoded in the video stream\. They are intended to help the downstream video player display content in a way that reflects the intentions of the content creator\.