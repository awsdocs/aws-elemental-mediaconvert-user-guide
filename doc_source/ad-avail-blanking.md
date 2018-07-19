# Blanking Out Content from Ad Avails<a name="ad-avail-blanking"></a>

You can enable Ad avail blanking to remove video content, remove any captions, and mute audio during the portions of the output that are marked as available for ads \(ad avails\)\. 

You set up whether there are SCTE\-35 markers for each output individually, but you enable or disable Ad avail blanking for every output in the job\. For the service to blank out portions of the output, you have to both pass through the markers and enable Ad avail blanking\.

**To enable Ad avail blanking:**

1. Create a job and set up outputs to include SCTE\-35 markers as described in [Including SCTE\-35 Markers in an Output](including-scte-35-markers-in-an-output.md)\.

1. In the left navigation pane, under **Job settings**, choose **Settings**\.

1. Under **Global processors**, enable **Ad avail blanking**\.

1. Optionally, under **Blanking image**, provide a URI to an image file located in an Amazon S3 bucket\. If you specify an image here, the service will insert the image on all video frames inside the ad avail\. If you don't specify an image, the service will use a black slate instead\.

   Blanking images must be \.png or \.bmp files that are the same size or smaller, in pixels, as the output video resolution\. 