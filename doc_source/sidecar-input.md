# IMSC, SCC, SMPTE\-TT, SRT, STL, TTML \(sidecar\) input captions<a name="sidecar-input"></a>

IMSC, SCC, SMPTE\-TT, SRT, STL, and TTML are sidecar captions formats\. With these formats, you provide input captions as a separate file\. Depending on your output captions settings, AWS Elemental MediaConvert passes them through to the output in the same format or converts them into another sidecar format\.

**IMSC captions**  
MediaConvert supports IMSC as an input captions format either as a sidecar file or as part of an IMF source\. If your input IMSC captions are part of an IMF package, see [IMSC input captions \(as part of an IMF source\)](IMSC-in-MXF.md)\. For restrictions on IMSC support, see [IMSC captions support in AWS Elemental MediaConvert](imsc-captions-support.md)\.

**SMPTE\-TT captions**  
You can use SMPTE\-TT input captions that are text\-only, that have captions images included in the captions file with base64 encoding \(`smpte:image encoding="Base64"`\), and that use external references to captions images \(`smpte:backgroundImage`\)\.

When your captions use external references to images, those images must be located in the same Amazon S3 bucket and folder as your captions file\. For example, say this is the S3 path to your SMPTE\_TT file: `AWSDOC-EXAMPLE-BUCKET/mediaconvert-input/captions/my-captions-spanish.ttml`\. Then you must store the image files that the captions file references here: `s3://AWSDOC-EXAMPLE-BUCKET/mediaconvert-input/captions/`\.

**All sidecar captions**  
In all cases, create one captions selector for each input captions file\.

In **Source file**, enter the URI to the captions input file that is stored in Amazon S3 or on an HTTP\(S\) server\. For Amazon S3 inputs, you can specify the URI directly or choose **Browse** to select from your Amazon S3 buckets\. For HTTP\(S\) inputs, provide the URL to your input video file\. For more information, see [HTTP input requirements](upload-input-files.md#http-input-requirements)\. 

**Synchronizing sidecar captions and video**  
To make sure that your captions are properly synchronized with your video, check that the value for **Timecode source** in the **Video selector** section matches the timecodes in your captions file\. For example, if your video has embedded timecodes starting at 01:00:00:00, but the timecodes in your captions file start at zero, change the default value for the video selector **Timecode source** from **Embedded** to **Start at 0**\. If other aspects of your job prevent that, use the **Time delta** setting to adjust your captions, as described in [Use cases for time delta](time-delta-use-cases.md)\.

**Note**  
MediaConvert handles the alignment of captions with video differently depending on whether the caption format is timecode\-based or timestamp\-based\. For more information, see [Input timecode source and captions alignment](about-input-timecode-source-and-captions-alignment.md)\.

Enter a positive or negative number in **Time delta** to modify the time values in the captions file\. By default, time delta is measured in seconds\. For example, enter **15** to add 15 seconds to all the time values in the captions file\. Or, enter **\-5** to subtract 5 seconds from the time values in the captions file\. To specify in milliseconds instead, set **Time delta units** to **Milliseconds**\.

If the value you enter for **Time delta** would result in captions before or after your video, those captions will not be present in your output\.

**Note**  
When converting from SCC to SRT, MediaConvert first rounds the value you set for **Time delta** to the nearest input frame\. MediaConvert uses this rounded value when calculating output SRT timings\.

**Topics**
+ [Input timecode source and captions alignment](about-input-timecode-source-and-captions-alignment.md)
+ [Use cases for time delta](time-delta-use-cases.md)
+ [Converting dual SCC input files to embedded captions](converting-dual-scc-input-files-to-embedded-captions.md)
+ [TTML style formatting](ttml-style-formatting.md)