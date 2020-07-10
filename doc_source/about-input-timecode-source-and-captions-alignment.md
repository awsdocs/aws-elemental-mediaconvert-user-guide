# Input timecode source and captions alignment<a name="about-input-timecode-source-and-captions-alignment"></a>

When you adjust your input timeline by setting the input **Timecode source** to **Start at 0** or **Specified start**, MediaConvert behaves as though your input has embedded timecodes that start when you specify\. But MediaConvert doesn't change the timecodes or timestamps in your sidecar captions files\. Therefore, the way that you align your captions depends on your captions format\.

**Timecode\-based sidecar formats \(SCC, STL\)**  
Some captions formats, including SCC and STL, define where captions are placed in the video by timecode\. With these formats, MediaConvert places each caption on the frames specified in the captions file, according to each frame's timecode in the input timeline\. To adjust your captions to start at a different time than that, use the **Time delta** setting\. For more information, see [Use cases for time delta](time-delta-use-cases.md)\.

MediaConvert establishes the input timeline based on the value you choose for the input **Timecode source** setting\.

For example, if your SCC file specifies that the first caption should appear at 00:05:23:00 and you set **Timecode source** to **Specified start** and **Start timecode** to 00:04:00:00, the first caption will appear in your output one minute and twenty\-three seconds into the video\. If you set **Timecode source** to **Specified start** and **Start timecode** to 01:00:00:00, you won't see captions when you expect, because 00:05:23:00 occurs before the start of your video, according to the input timeline\.

**Timestamp\-based sidecar formats \(SRT, SMI, TTML\)**  
Some captions formats, including SRT, SMI, and TTML, allow for definition of where captions are placed in the video by timestamp\. With these, MediaConvert measures the placement of the captions by the distance, in time, from the start of the video\. This is true regardless of whether the captions file specifies placement with timecode or timestamp\.

Therefore, your captions appear at the time specified in the captions file without regard to the video timecodes\. For example, if your SRT file specifies that the first caption should appear at 00:05:23:00 or at 00:05:23,000 and you set **Timecode source** to **Specified start** and **Start timecode** to 00:04:00:00, the first caption will still appear in your output five minutes and twenty\-three seconds into the video\.

To adjust your captions to start at a different time than that, use the **Time delta** setting\. For more information, see [Use cases for time delta](time-delta-use-cases.md)\.

**Formats that embed captions in the video stream \(CEA/EIA\-608, CEA/EIA\-708\)**  
Some captions formats embed the captions directly in the video frame or the video frame metadata\. With these, MediaConvert keeps the captions with the frames that they are embedded in, regardless of the timecode settings\.