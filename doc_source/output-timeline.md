# Output timeline<a name="output-timeline"></a>

The *output timeline* is the series of timecodes that MediaConvert generates to embed in the outputs\. MediaConvert also uses the timecodes of the output timeline for features that apply to every output in the job\.

By default, the output timeline is the same as any timecodes embedded in the video of your first input file\. You can specify a different starting timecode in the job\-wide **Timecode configuration** settings under **Job settings**\. If you use the API or an SDK, you can find these settings in the JSON file of your job\. These settings are under `Settings`, `TimecodeConfig`\. For more information, see [Adjusting the output timeline with the job\-wide timecode configuration](timecode-jobconfig.md)\.

MediaConvert uses the output timeline for the following:
+ Determining which timecodes to embed in the output video, when you enable **Timecode insertion** in your output timecode settings\.
+ Determining when output overlays \(inserted images\) appear in the video\. For more information about the different types of graphic overlays, see [Using image inserter \(graphic overlay\)](graphic-overlay.md)\.
+ Determining how your HLS variant playlists show time\.
+ Interpreting the timecode that you provide when you specify a value for **Anchor timecode**\.