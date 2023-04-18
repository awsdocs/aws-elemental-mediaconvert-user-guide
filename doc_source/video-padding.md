# Padding video with black video frames<a name="video-padding"></a>

## How black video padding works<a name="how-pad-video-works"></a>

AWS Elemental MediaConvert can pad video tracks with black video frames so that video and audio durations align\.

Input media files might have audio and video tracks with different durations\. In the following horizontal bar graph, the audio track starts before the video track and ends after it\.

![\[Horizontal bar graph where audio track extends before and after the video track.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/pad-video-example-1.png)

You can use **Pad video** to lengthen the video track\. In the **Input** pane, under **Video selector**, choose **Video correction** and set **Pad video** to `Black`\. Depending on your input, this generates black video frames at the beginning, end, or both the beginning and end, of your input\. 

In the following horizontal bar graph, black frames fill in the beginning and end of the video to match the length of the audio\.

![\[Horizontal bar graph with black frames filling the beginning and end of the video track.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/pad-video-example-2.png)

## Pad video FAQ<a name="pad-video-faq"></a>

**Q: Since video frames and audio samples have different rates, will AWS Elemental MediaConvert ever generate partial video frames?** 

MediaConvert generates full video frames\.

If you have a downstream workflow that is sensitive to very small duration differences between video and audio, set **Audio duration** to `Match video duration` in your output video settings\.

**Q: What if the starting presentation timestamps \(PTS\) in my input video and audio tracks are different?**

If your input video starts at 10 seconds and has a 30 second duration, and your input audio starts at 0 seconds and also has a 30 second duration, then 10 seconds of black video will be added to the beginning\.

**Q: What if the audio in my input starts *after* the video? Or the audio ends before the video?**

Audio silence is inserted at the beginning or end to align with the start or end of the video\.

**Q: Can I use input clipping instead to align audio and video durations?**

Yes, input clipping can help accomplish the same task of aligning audio and video durations\. But keep in mind that input clipping also removes audio or video content from the input\.

## Feature restrictions for Pad video<a name="pad-video-restrictions"></a>

The following feature is unavailable when you pad with black video:
+ Accelerated transcoding