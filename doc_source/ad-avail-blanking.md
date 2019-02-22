# Enabling Ad Avail Blanking<a name="ad-avail-blanking"></a>

You can enable ad avail blanking to remove video content, remove any captions, and mute audio during the portions of the output that are marked as available for ads \(ad avails\)\. 

You set up SCTE\-35 markers in each output individually, but you enable or disable ad avail blanking for every output in the job\. To use ad avail blanking, you have to both set up SCTE\-35 markers and enable ad avail blanking, as described in the following procedure\.

**To enable ad avail blanking \(console\)**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create new job**\.

1. Set up your input, output groups, and outputs for video and audio, following the procedure in [Passing Through SCTE\-35 Markers from Your Input](passing-through-scte-35-markers.md) or [Specifying SCTE\-35 Markers Using ESAM XML](specifying-scte-35-markers-using-esam-xml.md)\.

1. In the left navigation pane, under **Job settings**, choose **Settings**\.

1. Under **Global processors**, enable **Ad avail blanking**\.

1. Optionally, under **Blanking image**, provide a URI to an image file located in an Amazon S3 bucket\. If you specify an image here, the service inserts the image on all video frames inside the ad avail\. If you don't specify an image, the service uses a black slate instead\.

   Blanking images must be \.png or \.bmp files that are the same size or smaller, in pixels, as the output video resolution\. 