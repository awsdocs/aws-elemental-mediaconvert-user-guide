# Adjusting the Input Timecode Setting<a name="timecode-input"></a>

The value for **Timecode source** that you specify in the input settings affects how AWS Elemental MediaConvert synchronizes audio and captions that you provide in a file that is separate from the video\. These are called *sidecar* captions and audio files\.

Input **Timecode source** also affects how the service interprets the timecodes that you provide for input clipping\. For information about input clipping, see [Transcoding Only a Portion of Your Input \(Input Clipping\)](input-clipping-stitching.md)\.

**To adjust the **Timecode source** setting \(console\)**

1. On the **Create job** page, in the **Job** pane on the left, choose an input\.

1. Under **Video selector**, **Timecode source**, specify whether MediaConvert reads timecodes from the input or generates them\. MediaConvert can generate timecodes starting from zero or from a starting timecode that you specify\. Options for **Timecode source** are as follows:
   + **Embedded**: The service uses any timecodes embedded in the input video\. This is the default value\. 
**Note**  
Don't choose this value unless your input video has embedded timecodes\.
   + **Start at 0**: The service sets the timecode of the first frame of the input to 00:00:00:00\.
   + **Specified start**: The service sets the timecode of the first frame of the input to the value that you specify in the setting **Start timecode**\.

   Regardless of the source, timecodes are in the following 24\-hour format with a frame number: HH:MM:SS:FF\.

**To adjust the **Timecode source** setting \(API, SDK, and AWS CLI\)**  
If you use the API or an SDK, you can find this setting in the JSON file of your job, called `TimecodeSource`, located in `Settings`, `Inputs`\. For more information, see [InputTimecodeSource](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-model-inputtimecodesource) in the AWS Elemental MediaConvert API Reference\.

## About Input Timecode Source and Captions Alignment<a name="about-input-timecode-source-and-captions-alignment"></a>

When you adjust your input timecodes by setting the input **Timecode source** to **Start at 0** or **Specified start**, MediaConvert behaves as though your input has embedded timecodes that start when you specify\. The service doesn't change the timecodes or timestamps in your sidecar captions files\. Therefore, the way that you align your captions depends on your captions format\.

**Timecode\-Based Sidecar Formats \(SCC, STL\)**  
Some captions formats, including SCC and STL, define where captions are placed in the video by timecode\. With these, your captions appear on the frames specified in the captions file, after the service applies the new timecodes that you specify with **Timecode source**\.

For example, if your SCC file specifies that the first caption should appear at 00:05:23:00 and you set **Timecode source** to **Specified start** and **Start timecode** to 00:04:00:00, the first caption will appear in your output one minute and twenty\-three seconds into the video\. If you set **Timecode source** to **Specified start** and **Start timecode** to 01:00:00:00, the first caption won't appear at all in your output, because it occurs before the start of your video\.

To adjust your captions to start at a different time than that, use the **Time delta** setting\. For more information, see [Use Cases for Time Delta](time-delta-use-cases.md)\.

**Timestamp\-Based Sidecar Formats \(SRT, SMI, TTML\)**  
Some captions format, including SRT, SMI, and TTML, allow for definition of where captions are placed in the video by timestamp\. With these, MediaConvert measures the placement of the captions by the distance, in time, from the start of the video\. This is true regardless of whether the captions file specifies placement with timecode or timestamp\.

Therefore, your captions appear at the time specified in the captions file without regard to the video timecodes\. For example, if your SRT file specifies that the first caption should appear at 00:05:23:00 and you set **Timecode source** to **Specified start** and **Start timecode** to 00:04:00:00, the first caption will still appear in your output five minutes and twenty\-three seconds into the video\.

To adjust your captions to start at a different time than that, use the **Time delta** setting\. For more information, see [Use Cases for Time Delta](time-delta-use-cases.md)\.

**Formats That Embed Captions in the Video Stream \(CEA/EIA\-608, CEA/EIA\-708\)**  
Some captions formats embed the captions directly in the video frame or the video frame metadata\. With these, MediaConvert keeps the captions with the frames that they are embedded in, regardless of the timecode settings\.