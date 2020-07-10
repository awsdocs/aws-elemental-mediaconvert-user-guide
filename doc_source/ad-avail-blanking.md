# Enabling ad avail blanking<a name="ad-avail-blanking"></a>

You can enable ad avail blanking to remove video content, remove any captions, and mute audio during the portions of the output that are marked as available for ads \(ad avails\)\. 

You set up SCTE\-35 markers in each output individually, but you enable or disable ad avail blanking for every output in the job\. To use ad avail blanking, you have to both set up SCTE\-35 markers and enable ad avail blanking, as described in the following procedure\.

**To enable ad avail blanking \(console\)**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create new job**\.

1. Set up your input, output groups, and outputs for video and audio, following the procedure in [Passing through SCTE\-35 markers from your input](passing-through-scte-35-markers.md) or [Specifying SCTE\-35 markers using ESAM XML](specifying-scte-35-markers-using-esam-xml.md)\.

1. In the left navigation pane, under **Job settings**, choose **Settings**\.

1. Under **Global processors**, enable **Ad avail blanking**\.

1. Optionally, under **Blanking image**, provide a URI to an image input file that is stored in Amazon S3 or on an HTTP\(S\) server\. For Amazon S3 inputs, you can specify the URI directly or choose **Browse** to select from your Amazon S3 buckets\. For HTTP\(S\) inputs, provide the URL to your input video file\. For more information, see [HTTP input requirements](upload-input-files.md#http-input-requirements)\. 

   If you specify an image here, the service inserts the image on all video frames inside the ad avail\. If you don't specify an image, the service uses a black slate instead\.

   Blanking images must be \.png or \.bmp files that are the same size or smaller, in pixels, as the output video resolution\. 