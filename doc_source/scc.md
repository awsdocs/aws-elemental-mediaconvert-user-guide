# SCC, SRT, STL, TTML \(Sidecar\)<a name="scc"></a>

SCC, SRT, STL, and TTML are sidecar captions formats\. With these formats, you provide input captions as a separate file\. AWS Elemental MediaConvert handles all sidecar formats the same way\. The service can pass them through to the output in the same format or convert them into another sidecar format\. In all cases, you must create one captions selector for the entire set of captions tracks\.

Provide the following values for the captions selector fields:
+ **External captions file**: The URI to the captions file\. MediaConvert accepts captions files from Amazon S3\.
+ **Time delta**: \(Optional\) Use this setting if you need to adjust the sync between the captions and the video:
  + Type a positive number to add to the times in the captions file\. For example, type **15** to add 15 seconds to all the times in the captions file\.
  + Type a negative number to subtract from the times in the captions file\. For example, type **\-5** to subtract 5 seconds from the times in the captions file\.

    Enter the time delta in seconds, regardless of the format used in your captions file to specify start and end times\. The number that you enter for **Time delta** simply delays the captions or makes the captions play earlier, regardless of the timecode formats\.

**Note**  
To make sure that your captions are properly synchronized with your video, check that the value for **Timecode source** in the **Video selector** section matches the timecodes in your captions file\. For example, if the timecodes in your captions file start at zero but your video has embedded timecodes starting at 01:00:00:00, change the default value for **Timecode source** from **Embedded** to **Start at 0**\. If other aspects of your job prevent that, use the **Time delta** setting to adjust your captions, as described in [Use Cases for Time Delta](#time-delta-use-cases)\.  
If you use the API or an SDK, you can find this setting in the JSON file of your job, called `TimecodeSource`, located in `Settings`, `Inputs`\. When you use SCC, you must provide a value for `TimecodeSource`\. Otherwise, MediaConvert will not insert the captions\. 

## Use Cases for Time Delta<a name="time-delta-use-cases"></a>

How you use **Time delta** depends on the problem you're trying to solve and the captions format you're working with\.

**Adjusting for Different Timecodes Between Video and Captions Files**  
With timecode\-based captions formats, such as SCC and STL, the timecodes in the captions might be based on the assumption that the video timecodes start at a different timecode than they actually do\. You use **Time delta** to adjust for the difference\.

**Example problem:** For example, your video file might have embedded timecodes that start at 00:05:00:00 and the first instance of dialogue that requires captions might be one minute into the video, at timecode 00:06:00:00\. Your captions file might be written on the assumption that your video timecodes start at 00:00:00:00, with the first caption starting at 00:01:00:00\. If you don't use **Time delta**, MediaConvert would not include this first caption, because it occurs before the start of the video\. 

**Solution:** Add five minutes to the captions\. Enter **300** for **Time delta**\.

Similarly, your captions file might be aligned with the captions that are embedded in your video, but you might need to use the input **Timecode source** setting to change the input timecodes, which creates a difference between the video and captions\.

**Example problem:** For example, your video file might have embedded timecodes that start at 00:05:00:00 and the first instance of dialogue that requires captions might be one minute into the video, at timecode 00:06:00:00\. Your captions file is written to sync correctly, with the first caption starting at 00:06:00:00\. But you need to change your embedded captions at the input to sync correctly with your audio file\. So you set the input **Timecode source** to **Start at Zero**\. If you don't use **Time delta**, MediaConvert would put the first caption in your output at six minutes into the video\.

**Solution:** Subtract five minutes from the captions\. Enter **\-300** for **Time delta**\.

**Correcting Slight Errors in Captions Sync**  
With any type of sidecar format, there might be a small error in your input captions file, so that the captions are consistently a little late or a little early\.

**Example problem:** Your video has embedded captions that start at zero\. The first instance of dialogue that requires captions is at 00:06:15:00, but the captions appear on the screen three seconds late, at 00:06:18:00\.

**Solution:** Subtract three seconds from the captions\. Enter **\-3** for **Time delta**\.