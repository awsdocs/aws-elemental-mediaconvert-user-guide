# Setting Up Still Graphic Overlays in Outputs<a name="setting-up-still-graphic-overlays-in-outputs"></a>

Because you are setting up an output overlay, set up image insertion in each output where you want the service to overlay graphics on your video\. For information about setting up an overlay that appears on all outputs or on portions that correspond to only one input, see [Choosing Between Input Overlay and Output Overlay](choosing-between-input-overlay-and-output-overlay.md)\.

If you don't specify overlay start time and duration, the service puts the overlay on the entire output\.

**To set up a still graphic overlay in an output**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Set up your output groups and outputs for video and audio, as described in [Setting Up a Job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring Complex Jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\.

1. For each output that you want to have a graphic overlay, do the following:

   1. On the **Create job** page, in the **Job** pane on the left, under **Output groups**, choose the appropriate output\.

   1. Under **Encoding** settings, under the **Video** tab, find the **Preprocessors** section\.

   1. Choose **Image inserter**\. This displays an **Add image** button\.

   1. For each graphic overlay that you want to include in the output, choose **Add image**, and then specify the overlay settings\.

For details about the more complex output graphic overlay settings, see the following topics:

[About Sizing Your Overlay to Account for Scaling](about-overlay-scaling.md)

[About Specifying **Layer**](using-multiple-overlays.md)