# Use cases for time delta<a name="time-delta-use-cases"></a>

How you use **Time delta** depends on the problem you're trying to solve and the captions format that you're working with\.

## Adjusting for different timecodes between video and captions files<a name="adjusting-for-different-timecodes-between-video-and-captions-files"></a>

With timecode\-based captions formats, such as SCC and STL, the timecodes in the captions might be relative to a starting timecode that is different from the starting timecode embedded in the video\. You use **Time delta** to adjust for the difference\.

**Example problem:** Your video file might have embedded timecodes that start at 00:05:00:00 and the first instance of dialogue that requires captions might be one minute into the video, at timecode 00:06:00:00\. Your captions file might be written on the assumption that your video timecodes start at 00:00:00:00, with the first caption starting at 00:01:00:00\. If you don't use **Time delta**, MediaConvert would not include this first caption because it occurs before the start of the video\. 

**Solution:** Add five minutes to the captions\. Enter **300** for **Time delta**\.

## Adjusting captions after synchronizing video and audio<a name="adjusting-captions-after-sychronizing-video-and-audio"></a>

Your timecode\-based \(SCC or STL\) captions might be aligned with the timecodes that are embedded in your video, but you might need to use the input **Timecode source** setting to align your audio\. This creates a difference between the video and captions, which you need to adjust for\. You don't need to make this adjustment with timestamp\-based captions formats, such as SRT, SMI, and TTML\.

For more information about aligning captions when you use input **Timecode source**, see [Input timecode source and captions alignment](about-input-timecode-source-and-captions-alignment.md)\.

**Example problem:** Your video file might have embedded timecodes that start at 00:05:00:00 and the first instance of dialogue that requires captions might be one minute into the video, at timecode 00:06:00:00\. Your captions file is written to sync correctly, with the first caption starting at 00:06:00:00\. But you need to change your embedded captions in your input to sync correctly with your audio file\. So you set the input **Timecode source** to **Start at Zero**\. If you don't use **Time delta**, MediaConvert would put the first caption in your output at six minutes into the video\.

**Solution:** Subtract five minutes from the captions\. Enter **\-300** for **Time delta**\.

## Correcting slight errors in captions sync<a name="correcting-slight-errors-in-captions-sync"></a>

With any type of sidecar format, there might be a small error in your input captions file, so that the captions are consistently a little late or a little early\.

**Example problem:** Your video has embedded captions that start at zero\. The first instance of dialogue that requires captions is at 00:06:15:00, but the captions appear on the screen three seconds late, at 00:06:18:00\.

**Solution:** Subtract three seconds from the captions\. Enter **\-3** for **Time delta**\.