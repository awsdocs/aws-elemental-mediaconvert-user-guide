# Motion image inserter \(graphic overlay\) in AWS Elemental MediaConvert<a name="motion-graphic-overlay"></a>

The following topics walk you through how to set up motion graphic overlays\. Motion graphic overlays appear in all outputs\. 

By default, if you don't specify an overlay start time or set playback to repeat, the overlay begins at the start of the video and runs for the duration of the motion graphic that you provide\.

## Placing your motion graphic overlay<a name="placing-your-motion-graphic-overlay"></a>

When you place a motion graphic overlay, you set up when it starts and how long it runs by specifying the **Start time** and **Playback**\. The following image shows how you would specify these settings if you wanted your overlay to start two minutes into the video and to continuously loop over the rest of the video\. If you keep **Start time** and **Playback** in their default state, the overlay will begin at the first frame of each output and remain on the video for the duration of the motion graphic played once\.

**Note**  
In this example, the motion graphic is three minutes long, but the overlay is set to continue to repeat the motion graphic until the end of the output\.

![\[The overlay is represented in this image as a rectangle above a number line. The number line is marked with timecodes at one minute apart. The left edge of the rectangle is aligned with the second mark, at 00:00:02:00. The right edge of the rectangle is aligned with the fourth mark, at 00:00:04:00.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/MotionOverlayStartDuration.png)

**Start time**  
Provide the timecode for the first frame that you want to have the motion overlay appear on\. This timecode is relative to your input timeline\. For input overlays, **Start time** is relative to the input timeline\. This timeline is affected by the input **Timecode source** setting\.

For input overlays, **Start time** is relative to the input timeline\. This timeline is affected by the input **Timecode source** setting\.

For more information about the input and output timelines, and the timecode settings that affect them, see [How MediaConvert uses timelines to assemble jobs](how-mediaconvert-uses-timelines-to-assemble-jobs.md)\. For jobs with multiple inputs, MediaConvert places the motion overlay on each input, according to the input timeline for that input\. You specify **Start time** once, and MediaConvert applies that value to all inputs\.

**Tip**  
For simplest setup, specify **Start time** counting from 00:00:00:00 as the first frame, and set both of the following settings to **Start at 0**:  
**Timecode configuration**, **Source**, under the job\-wide settings\.
**Timecode source**, in the **Video selector** settings for each input\.

****Playback****  
You can set your overlay to last the duration of the motion graphic played through once, or you can set it to loop the motion graphic continuously from the start time to the end of the output\. The duration of a \.mov motion graphic is built into the \.mov file, which has a set number of frames and a defined frame rate\. If your motion graphic is a set of \.png images, you determine the duration of the overlay by how many images you provide and the frame rate that you specify\. The duration in seconds is the number of frames divided by the frame rate in frames per second\. For example, if your frame rate is 30 fps and you provide 600 images, the duration of the motion overlay is 20 seconds\.

For jobs with multiple inputs, MediaConvert places the motion overlay on each input at the time that you specify for **Start time**, and then either plays the overlay once or until the end of the input, depending on what you choose for **Playback**\. You specify **Playback** once, and MediaConvert applies that value to all inputs\.

## Requirements for the motion overlay file<a name="requirements-for-the-motion-overlay-file"></a>

**General requirements for motion graphic files**  
Set up the files for your motion graphic as follows:
+ **File type**: Use \.mov or a set of sequential \.png files\.
+ **Frame rate**: Use any frame rate; it doesn't have to match the frame rate of the underlying video\. Frame rate is embedded in \.mov files; with a set of \.png files you specify the frame rate when you set up the overlay\.
+ **Aspect ratio**: Use any aspect ratio; it doesn't have to match the aspect ratio of the underlying video\.
+ **Size in pixels**: Use any size\. AWS Elemental MediaConvert scales the motion graphic with any outputs that have video scaling\.

**Additional requirements for sets of sequential \.png files**  
Set up your \.png motion image files follows:
+ Make sure that the names of the \.png files end with sequential numbers that specify the order that they are played in\. For example, overlay\_000\.png, overlay\_001\.png, overlay\_002\.png, and so on\.
+ Pad your initial file name with enough zeros to complete the sequence\. For example, if the first image is overlay\_0\.png, there can be only 10 images in the sequence, with the last image being overlay\_9\.png\. But if the first image is overlay\_00\.png, there can be 100 images in the sequence\.
+ Make sure that the number of images in your series matches the frame rate and your intended overlay duration\. For example, if you want a 30\-second overlay at 30 fps, you should have 900 \.png images\.

## Setting up motion graphic overlays<a name="setting-up-motion-graphic-overlays"></a>

Because motion graphic overlays apply to every output in the job, you set them up as a processor in the settings that apply to the entire job\.

You can set up still graphic overlays that appear only on individual outputs\. For information, see [Choosing between input overlay and output overlay](choosing-between-input-overlay-and-output-overlay.md)\.

**To set up a motion graphic overlay**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Set up your job, as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. On the **Create job** page, in the **Job** pane on the left, under **Job settings**, choose **Settings**\.

1. In the **Global processors** section to the right of the **Job** pane, enable **Motion image inserter**\.

1. For **Input**, specify your motion graphic file name\. If you're using a series of \.png files, provide the file name of the first image\.

1. Specify values for the other fields\. For more information about these fields, choose the **Info** link on the console next to **Motion image inserter**\.