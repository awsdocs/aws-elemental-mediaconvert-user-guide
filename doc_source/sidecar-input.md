# IMSC, SCC, SRT, STL, TTML \(sidecar\)<a name="sidecar-input"></a>

AWS Elemental MediaConvert supports IMSC as an input captions format either as a sidecar file or as part of an IMF source\. If your input IMSC captions are part of an IMF package, see [IMSC \(as part of an IMF source\)](IMSC-in-MXF.md)\. For restrictions on IMSC support, see [IMSC captions support in AWS Elemental MediaConvert](imsc-captions-support.md)\.

IMSC, SCC, SRT, STL, and TTML are sidecar captions formats\. With these formats, you provide input captions as a separate file\. Depending on your output captions settings, the service passes them through to the output in the same format or converts them into another sidecar format\.

In all cases, you create one captions selector for each input captions file\.

Provide the following values for the captions selector fields:
+ **External captions file**: The URI to the captions input file that is stored in Amazon S3 or on an HTTP\(S\) server\. For Amazon S3 inputs, you can specify the URI directly or choose **Browse** to select from your Amazon S3 buckets\. For HTTP\(S\) inputs, provide the URL to your input video file\. For more information, see [HTTP input requirements](upload-input-files.md#http-input-requirements)\. 
+ **Time delta**: \(Optional\) Use this setting if you need to adjust the sync between the captions and the video\. For more information, see [Use cases for time delta](time-delta-use-cases.md)\.

  Enter a positive or negative number to modify the times in the captions file\. For example, type **15** to add 15 seconds to all the times in the captions file\. Type **\-5** to subtract 5 seconds from the times in the captions file\.

  Enter the time delta in seconds, regardless of the format used in your captions file to specify start and end times\. The number that you enter for **Time delta** simply delays the captions or makes the captions play earlier, regardless of the timecode formats\.

**Synchronizing sidecar captions and video**  
To make sure that your captions are properly synchronized with your video, check that the value for **Timecode source** in the **Video selector** section matches the timecodes in your captions file\. For example, if the timecodes in your captions file start at zero but your video has embedded timecodes starting at 01:00:00:00, change the default value for **Timecode source** from **Embedded** to **Start at 0**\. If other aspects of your job prevent that, use the **Time delta** setting to adjust your captions, as described in [Use cases for time delta](time-delta-use-cases.md)\.

If you use the API or an SDK, you can find this setting in the JSON file of your job\. The setting name is `TimecodeSource`, located in `Settings`, `Inputs`\. 

**Note**  
MediaConvert handles the alignment of captions with video differently depending on whether the caption format is timecode\-based or timestamp\-based\. For more information, see [Input timecode source and captions alignment](about-input-timecode-source-and-captions-alignment.md)\.

**Topics**
+ [Input timecode source and captions alignment](about-input-timecode-source-and-captions-alignment.md)
+ [Use cases for time delta](time-delta-use-cases.md)
+ [Converting dual SCC input files to embedded captions](converting-dual-scc-input-files-to-embedded-captions.md)