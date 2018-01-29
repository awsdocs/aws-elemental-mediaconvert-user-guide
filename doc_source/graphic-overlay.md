# Including Graphic Overlays with AWS Elemental MediaConvert Image Inserter<a name="graphic-overlay"></a>

The image inserter \(graphic overlay\) feature lets you insert an image \(a BMP, PNG, or TGA file\) at a specified time and display it as an overlay on the underlying video for a specified duration\. This feature includes fade\-in and fade\-out capability and adjustable opacity\. You can include up to eight overlays in an output\.

For example, you might include a logo in the corner of the video frame throughout the duration of the file and an HDR indicator for only the portions of the file that are HDR\.

## Requirements for the Overlay File<a name="requirements-for-the-overlay-file"></a>

Set up the image files that you want to insert over your video as follows:

+ **File type**: Use \.bmp, \.png, or \.tga

+ **Aspect ratio**: Use any aspect ratio; it doesn't need to match the aspect ratio of the underlying video\.

+ **Size in pixels**: Use any size, up to the size of the underlying video\. 
**Note**  
In jobs that scale the video resolution \(that is, the size of the video frame\), the overlaid image is not scaled\. Make sure that the image that you select is scaled to suit the size of the video frame after scaling\.

## Setting Up Image Insertion<a name="setting-up-a-graphic-overlay"></a>

You set up image insertion individually in each output where you want the service to overlay graphics on your video\. 

**To insert an image over your video**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Set up your output groups and outputs for video and audio, as described in [Setting Up a Job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring Complex Jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\.

1. In the left pane of the **Create job** page, choose the appropriate output from the list of outputs\.

1. Under **Encoding** settings, under the **Video** tab, find the **Preprocessors** section\.

1. Choose **Image inserter**\. This displays an **Add image** button\.

1. Choose **Add image**\.

1. Specify the location of your overlay image and values for the settings to control how the overlay appears on the video\. For details about each setting, choose the **Info** link next to the setting\.

1. Repeat steps 6 and 7 to add any additional images that you want to include in this output\.

1. Repeat steps 3 through 8 for each output that you want AWS Elemental MediaConvert to overlay graphics on\.

## About Multiple Overlays<a name="using-multiple-overlays"></a>

You can set up an output with multiple overlay images\. Each overlay is independent of the others, with its own settings for opacity, fade\-in and fade\-out times, position on the frame, and the length of time that it is on the video\. You can set up overlays so that they all appear on the underlying video at the same time and physically overlap each other\. 

If you position overlay images so that they overlap, AWS Elemental MediaConvert layers them according to the value that you provide for the **Layer** setting\. The service overlays graphics with higher values for **Layer** on top of overlays with lower values for **Layer**\. 

\.