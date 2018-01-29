# Adjusting the Input Timecode Setting<a name="timecode-input"></a>

The value for **Timecode source** that you specify in the input settings affects how the service synchronizes audio and captions that you provide in a file that is separate from the video\. It also affects how the service interprets the timecodes that you provide for input clipping\. For information about input clipping, see [[ERROR] BAD/MISSING LINK TEXT](input-clipping-stitching.md)\.

**To adjust the **Timecode source** setting**

1. On the **Create job** page, in the **Job** pane on the left, choose an input\.

1. Under **Video selector**, **Timecode source**, specify whether AWS Elemental MediaConvert reads timecodes from the input or generates them starting from zero\. Options are as follows:

   + **Embedded**: The service uses any timecodes embedded in the input video\. This is the default value\. 

     If there are no embedded timecodes in the input, the service behaves as though **Timecode source** were set to **Start at 0**\.

   + **Start at 0**: The service sets the timecode of the first frame of the job to 00:00:00:00\.

   + **Specified start**: Do not use this option\.

   Regardless of the source, timecodes are in the following 24\-hour format with a frame number: HH:MM:SS:FF\.

   If you use the API or an SDK, you can find this setting in the JSON file of your job, called `TimecodeSource`, located in `Settings`, `Inputs`\.