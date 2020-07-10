# Step 1: Specify your input files<a name="specify-input-settings"></a>

The first part of setting up an AWS Elemental MediaConvert job is specifying the location of your input file or files, as shown in the following illustration\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/Job_input.png)

**To specify the location of your input**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the **Create job** page, in the **Job** pane on the left, choose **Input 1**\.

1. In the **Input 1** pane, provide the URI to your video input file that is stored in Amazon S3 or on an HTTP\(S\) server\. For Amazon S3 inputs, you can specify the URI directly or choose **Browse** to select from your Amazon S3 buckets\. For HTTP\(S\) inputs, provide the URL to your input video file\. For more information, see [HTTP input requirements](upload-input-files.md#http-input-requirements)\. 
**Note**  
If your input audio or captions are in a separate file, don't create separate inputs for them\. You specify these files later in this procedure, within your audio and captions selectors\.

1. To join more than one input file into a single asset \(input stitching\), add another input to the job\. To do so, in the **Job** pane, in the **Inputs** section, choose **Add**\. For jobs that have multiple input files, AWS Elemental MediaConvert creates outputs by concatenating the inputs in the order that you specify them in the job\.

   You can include up to 150 inputs in your job\.
**Tip**  
You can also transcode only portions of your inputs\. For more information, see [Assembling multiple inputs and input clips](assembling-multiple-inputs-and-input-clips.md)\.