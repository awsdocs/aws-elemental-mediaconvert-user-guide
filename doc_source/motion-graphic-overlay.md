# Motion image inserter \(graphic overlay\) in AWS Elemental MediaConvert<a name="motion-graphic-overlay"></a>

In this guide, you'll learn how to set up motion graphic overlays with AWS Elemental MediaConvert\. Motion graphic overlays appear in all outputs\. 

In the default setting for **Start time**, the overlay starts at the first frame of each output\. In the default setting for **Playback**, the overlay remains on the video for the duration of the motion graphic \(played once\)\. However, you can change the default setting by specifying an overlay start time, or by setting playback to repeat\. This guide shows you how\.



## Specify motion graphic overlay start time and playback<a name="placing-your-motion-graphic-overlay"></a>

You can specify motion graphic overlay **Start time** and **Playback** settings instead of using the default setting\. The following information shows how to specify overlay start time for a video and to repeat it continuously \(loop\)\. 



In the following image, the motion graphic overlay setting is three minutes long\. The motion graphic playback is set to repeat until the end of the output\.

![\[Motion graphic overlay setting at three minutes with playback set to repeat until the end of output.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/MotionOverlayStartDuration.png)

**Start time settings for motion overlays**  
Provide the timecode for the first frame where you want the motion overlay to appear\. This timecode is relative to your input timeline\. 

## Storage management<a name="specifying-overlay-start-time"></a>

For input overlays, **Start time** is relative to the input timeline\. This timeline is affected by the input **Timecode source** setting\.

For more information about the input and output timelines, and the timecode settings that affect them, see [How MediaConvert uses timelines to assemble jobs](how-mediaconvert-uses-timelines-to-assemble-jobs.md)\. For jobs with multiple inputs, MediaConvert places the motion overlay on each input, according to the input timeline for that input\. After you specify **Start time** once, MediaConvert applies that value to all inputs\.

**Tip**  
To simplify setup, specify **Start time** counting from 00:00:00:00 as the first frame, and set both of the following settings to **Start at 0**:  
**Timecode configuration**, **Source**, under the job\-wide settings\.
**Timecode source**, in the **Video selector** settings for each input\.

**Playback settings for motion graphic overlays**  
For playback settings on motion graphic overlays, you have two options\. You can set your overlay to play once through the duration of the motion graphic or to loop from the start time to the end of the output\. The duration of a \.mov motion graphic is built into the \.mov file, which has a set number of frames and a defined frame rate\. 

When a motion graphic is a set of \.png images, determine the duration of the overlay by how many images you provide and the frame rate that you specify\. The duration in seconds is the number of frames divided by the frame rate, in frames per second\. For example, if your frame rate is 30 fps and you provide 600 images, the duration of the motion overlay is 20 seconds\.

For jobs with multiple inputs, MediaConvert places the motion overlay on each input at the time that you specify for **Start time**\. Depending on what you choose for **Playback**, MediaConvert either plays the overlay once or until the end of the input\. When you specify **Playback** once, MediaConvert applies that value to all inputs\.

## Requirements to set up motion graphic overlay files<a name="requirements-for-the-motion-overlay-file"></a>

The following table describes how to set up motion graphic overlay files\.


| Motion graphic file requirement | Description | 
| --- | --- | 
| File type |  QuickTime \(\.mov\) [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/motion-graphic-overlay.html) Sequential PNG \(\.png\) [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/motion-graphic-overlay.html)  | 
| Frame rate |  QuickTime \(\.mov\) [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/motion-graphic-overlay.html) Sequential PNG \(\.png\) [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/motion-graphic-overlay.html)  | 
| Aspect ratio | Use any aspect ratio\. It doesn't have to match the aspect ratio of the underlying video\. | 
| Size in pixels | Use any size\. MediaConvert scales the motion graphic with any outputs that have video scaling\. | 

## Setting up motion graphic overlays<a name="setting-up-motion-graphic-overlays"></a>

Motion graphic overlays apply to every output in the job\. Therefore, set them up as a processor in the settings that apply to the entire job\.

You can set up still graphic overlays that appear only on individual outputs\. For information, see [Choosing between input overlay and output overlay](choosing-between-input-overlay-and-output-overlay.md)\.

**To set up a motion graphic overlay**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Set up your job, as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. On the **Create job** page, in the **Job** pane on the left, under **Job settings**, choose **Settings**\.

1. In the **Global processors** section to the right of the **Job** pane, enable **Motion image inserter**\.

1. For **Input**, specify your motion graphic file name\. If you're using a series of \.png files, provide the file name of the first image\.

1. Specify values for the other fields\. For more information about these fields, choose the **Info** link on the console next to **Motion image inserter**\.