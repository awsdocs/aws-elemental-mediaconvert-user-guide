# Setting up still graphic overlays in inputs<a name="setting-up-still-graphic-overlays-in-inputs"></a>

Because you are setting up an input overlay, set up image insertion in each input where you want the service to overlay graphics on your video\. The overlays that you specify appear in every output\. For information about setting up an overlay that appears on only specific outputs, see [Choosing between input overlay and output overlay](choosing-between-input-overlay-and-output-overlay.md)\.

If you don't specify overlay start time and duration, the service puts the overlay on the entire part of the output that corresponds to the input\.

**To set up a still graphic overlay in an output**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Specify your input files, as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. For each input that you want to have a graphic overlay, do the following:

   1. On the **Create job** page, in the **Job** pane on the left, under **Inputs**, choose the appropriate input\.

   1. In the **Image inserter** section to the right of the **Job** pane, choose **Add image**, and then specify the overlay settings\.

      For **Image location**, specify an input file that is stored in Amazon S3 or on an HTTP\(S\) server\. For Amazon S3 inputs, you can specify the URI directly or choose **Browse** to select from your Amazon S3 buckets\. For HTTP\(S\) inputs, provide the URL to your input video file\. For more information, see [HTTP input requirements](upload-input-files.md#http-input-requirements)\. 

For details about the more complex input graphic overlay settings, see the following topics:

[About sizing your overlay to account for scaling](about-overlay-scaling.md)

[About specifying **Layer**](using-multiple-overlays.md)