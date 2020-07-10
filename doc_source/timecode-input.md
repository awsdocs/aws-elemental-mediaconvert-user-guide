# Adjusting the input timeline with the input timecode source<a name="timecode-input"></a>

The value for **Timecode source** that you specify in an input's settings affects the input timeline for that input\. For information about which features are affected by the input timeline, see [Input timelines](input-timelines.md)\.

**To adjust the input **Timecode source** setting \(console\)**

1. On the **Create job** page, in the **Job** pane on the left, choose an input\.

1. Under **Video selector**, **Timecode source**, specify whether MediaConvert reads timecodes from the input or generates them\. MediaConvert can generate timecodes starting from zero or from a starting timecode that you specify\. Here are the options for **Timecode source**:
   + **Embedded**: The service uses any timecodes embedded in the input video\. This is the default value\. 
**Note**  
Don't choose this value unless your input video has embedded timecodes\.
   + **Start at 0**: The service sets the timecode of the first frame of the input to 00:00:00:00\.
   + **Specified start**: The service sets the timecode of the first frame of the input to the value that you specify in the setting **Start timecode**\.

   Regardless of the source, timecodes are in the following 24\-hour format with a frame number: HH:MM:SS:FF\.

**To adjust the input `TimecodeSource` \(**Timecode source**\) setting \(API, SDK, and AWS CLI\)**
+ In your JSON job specification, set a value for [TimecodeSource](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-model-inputtimecodesource), located in `Settings`, `Inputs`\.

  Choose a value for `TimecodeSource` as follows:
  + **EMBEDDED**: The service uses any timecodes embedded in the input video\. This is the default value\. 
**Note**  
Don't choose this value unless your input video has embedded timecodes\.
  + **ZEROBASED**: The service sets the timecode of the first frame of the input to 00:00:00:00\.
  + **SPECIFIEDSTART**: The service sets the timecode of the first frame of the input to the value that you specify in the setting **Start timecode**\.