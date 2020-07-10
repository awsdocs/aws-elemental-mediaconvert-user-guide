# Choosing your ABR streaming output groups<a name="choosing-your-streaming-output-groups"></a>

To create media assets for people to stream to their devices, choose one or more of the adaptive bitrate \(ABR\) output groups: Apple HLS, DASH ISO, Microsoft Smooth Streaming, or CMAF\. The type of output group determines which media players can play the files that MediaConvert creates from that output group\.

**Note**  
When you set up CMAF, DASH ISO, or Microsoft Smooth Streaming output groups, make sure to set your fragment length correctly\. For information about setting fragment length, see [Setting the fragment length for streaming outputs](setting-the-fragment-length.md)\.

The following table summarizes the relationships between output groups and media players\.


| For playing on\.\.\. | Use this output group\.\.\. | 
| --- | --- | 
| Apple devices, older | Apple HLS | 
| Apple devices, newer | CMAF | 
| Android devices, most smart TVs | CMAF or DASH ISO | 
| Microsoft devices | Microsoft Smooth Streaming | 

**Note**  
MediaConvert bills per minute of transcoded output time, not per job\. Therefore, when you add output groups to a job, it becomes more expensive\.   
For example, a job with an Apple HLS package and a DASH ISO package costs twice as much as a job with only one of those packages, assuming the transcoding settings are the same\.

**To determine which output groups you need**

1. Decide which devices you want end viewers to be able to play the transcoded media asset on\. If you want your asset to play on every possible device, include these output groups:
   + Apple HLS
   + DASH ISO or CMAF
   + Microsoft Smooth Streaming

1. Consider whether to use advanced encoding features\. To deliver either of the following to Apple devices, you must also include a CMAF output group:
   + High\-dynamic\-range \(HDR\) video
   + H\.265 \(HEVC\) encoded video

   If you include a CMAF output, you don't need to create a DASH ISO output because all the common DASH\-compatible players are also CMAF\-compatible\. 
**Note**  
There are a few uncommon DASH players that explicitly require the video segmentation extension type \.mp4\. MediaConvert outputs CMAF video segments in the \.cmfv format\. To create output that is compatible with these players, include a DASH ISO output group in your job\.

1. Consider cost trade\-off\.

   If you don't need to support players produced earlier than approximately 2013, and if you don't need to support the rare DASH players that require \.mp4 video segments, you can include a single CMAF output group instead of both DASH ISO and Apple HLS\. Creating a single CMAF package instead of separate DASH ISO and Apple HLS packages can also offer cost savings in your video storage and distribution, because you need to store and distribute only one set of video and audio files\.