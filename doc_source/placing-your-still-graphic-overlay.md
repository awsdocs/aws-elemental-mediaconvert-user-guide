# Placing your still graphic overlay<a name="placing-your-still-graphic-overlay"></a>

Whether your still graphic overlay is in input or output, set up the **Start time** and **Duration**\. The following image shows how to specify settings so that an overlay starts two minutes into the video and remains on the video for two minutes\. In the default settings, the overlay begins at the first frame of the input or output\. The overlay remains on the video for the duration of the input or output\.

![\[Graphic overlay start time at two minutes into the video and remaining on the video for two minutes.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/PlacingOverlay.png)

**Start time**  
Provide the timecode for the first frame that you want to have the overlay appear on\. If you set up your overlay to fade in, the fade\-in begins at the start time\.



When you provide your start time, choose one of the following timelines to suit the overlay that you're using:
+ For input overlays, **Start time** is relative to the input timeline\. This timeline is affected by the input **Timecode source** setting\.
+ For output overlays, **Start time** is relative to the output timeline\. This timeline is affected by the job\-wide **Timecode configuration**, **Source** setting\.

For more information about the input and output timelines, and the timecode settings that affect them, see [How MediaConvert uses timelines to assemble jobs](how-mediaconvert-uses-timelines-to-assemble-jobs.md)\.

**Tip**  
For simplest setup, specify **Start time** counting from 00:00:00:00 as the first frame, and set both of the following settings to **Start at 0**:  
**Timecode configuration**, **Source**, under the job\-wide settings\.
**Timecode source**, in the **Video selector** settings for each input\.

**Duration**  
Specify the length of time, in milliseconds, for the overlay duration to remain\. This duration includes fade\-in time, but not fade\-out time, as the following image shows\.

![\[Overlay fade-in time when the overlay is at full opacity, and the time when the overlay is fading out.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/OverlayFadeinFadeoutDuration.png)