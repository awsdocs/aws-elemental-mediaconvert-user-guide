# Placing your still graphic overlay<a name="placing-your-still-graphic-overlay"></a>

Regardless of whether you specify a still graphic overlay in an input or an output, you set up when it starts and how long it runs by specifying the **Start time** and **Duration**\. The following image shows how you would specify these settings if you wanted your overlay to start two minutes into the video and to remain on the video for two minutes\. If you keep these settings in their default state, the overlay will begin at the first frame of the input or output and remain on the video for the duration of the input or output\.

![\[The overlay is represented in this image as a rectangle above a number line. The number line is marked with timecodes at one minute apart. The left edge of the rectangle is aligned with the second mark, at 00:00:02:00. The right edge of the rectangle is aligned with the fourth mark, at 00:00:04:00.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/PlacingOverlay.png)

**Start time**  
Provide the timecode for the first frame that you want to have the overlay appear on\. If you set up your overlay to fade in, the fade\-in begins at the start time\.

Make sure that you take the right timeline into account when you provide your start time\. This depends on which overlay you're using:
+ For input overlays, **Start time** is relative to the input timeline\. This timeline is affected by the input **Timecode source** setting\.
+ For output overlays, **Start time** is relative to the output timeline\. This timeline is affected by the job\-wide **Timecode configuration**, **Source** setting\.

For more information about the input and output timelines, and the timecode settings that affect them, see [How MediaConvert uses timelines to assemble jobs](how-mediaconvert-uses-timelines-to-assemble-jobs.md)\.

**Tip**  
For simplest setup, specify **Start time** counting from 00:00:00:00 as the first frame, and set both of the following settings to **Start at 0**:  
**Timecode configuration**, **Source**, under the job\-wide settings\.
**Timecode source**, in the **Video selector** settings for each input\.

**Duration**  
Specify the length of time, in milliseconds, that you want the overlay to remain for\. This duration includes fade\-in time, but not fade\-out time, as the following image shows\.

![\[This image shows three rectangles, representing the time when the overlay is fading in, the time when the overlay is at full opacity, and the time when the overlay is fading out. A brace labeled "Duration" surrounds the first two boxes.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/OverlayFadeinFadeoutDuration.png)