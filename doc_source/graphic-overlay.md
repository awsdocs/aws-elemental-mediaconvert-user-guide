# Using Graphic Overlay \(Image Inserter\) in AWS Elemental MediaConvert<a name="graphic-overlay"></a>

The image inserter \(graphic overlay\) feature lets you insert an image \(a PNG or TGA file\) at a specified time and display it as an overlay on the underlying video for a specified duration\. This feature includes fade\-in and fade\-out capability and adjustable opacity\.

You can set up an output with multiple overlay images\. For example, you might include a logo in the corner of the video frame throughout the duration of the file and an HDR indicator for only the portions of the file that are HDR\.

Each overlay is independent of the others, with its own settings for opacity, fade\-in and fade\-out times, position on the frame, and the length of time that it is on the video\. You can set up overlays so that they all appear on the underlying video at the same time and physically overlap each other\.

## Requirements for the Overlay File<a name="requirements-for-the-overlay-file"></a>

Set up the image files that you want to insert over your video as follows:
+ **File type**: Use \.png or \.tga\.
+ **Aspect ratio**: Use any aspect ratio; it doesn't need to match the aspect ratio of the underlying video\.
+ **Size in pixels**: Use any size\. In jobs that scale the video resolution \(that is, the size of the video frame\), the service doesn't scale overlaid graphics\. If the overlaid graphic is larger than the output video frame, the service crops the graphic at the edge of the frame\.

## Setting Up Graphic Overlay<a name="setting-up-a-graphic-overlay"></a>

Set up image insertion individually in each output where you want the service to overlay graphics on your video\. 

**To insert an image over your video**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Set up your output groups and outputs for video and audio, as described in [Setting Up a Job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring Complex Jobs in MediaConvert](structuring-complex-jobs.md)\.

1. For each output that you want to have a graphic overlay, do the following:

   1. In the left pane of the **Create job** page, choose the appropriate output from the list of outputs\.

   1. Under **Encoding** settings, under the **Video** tab, find the **Preprocessors** section\.

   1. Choose **Image inserter**\. This displays an **Add image** button\.

   1. For each graphic overlay that you want to include in the output, choose **Add image**, and then specify the overlay settings\.

For details about the more complex graphic overlay settings, see the following topics\.

**Topics**
+ [About Specifying the Overlay Start Time](about-specifying-overlay-start-time.md)
+ [About Specifying the Overlay **Layer**](using-multiple-overlays.md)