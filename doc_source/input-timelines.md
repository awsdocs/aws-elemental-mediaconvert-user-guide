# Input timelines<a name="input-timelines"></a>

Each input has its own *input timeline*\. An input timeline is a series of timecodes that MediaConvert generates to represent each frame of the input file\.

By default, the input timeline is the same as any timecodes embedded in the input video\. You can specify a different starting timecode in the input setting **Timecode source**\. If you use the API or an SDK, you can find this setting in the JSON file of your job\. The setting name is `TimecodeSource`, located in `Settings`, `Inputs`\. For more information, see [Adjusting the input timeline with the input timecode source](timecode-input.md)\.

MediaConvert uses the input timeline for the following:
+ Determining when input graphic overlays \(inserted images\) appear in the video\. For more information about the difference between input and output overlays, see [Choosing between input overlay and output overlay](choosing-between-input-overlay-and-output-overlay.md)\.
+ Determining when motion graphic overlays \(inserted images\) appear in the video\. For more information about the different types of graphic overlays, see [Using image inserter \(graphic overlay\)](graphic-overlay.md)\.
+ Synchronizing your video with *sidecar captions* that are in a timecode\-based format\. Sidecar captions are captions that you provide as input files that are separate from the video\.
+ Interpreting the timecodes that you provide when you specify input clips\.