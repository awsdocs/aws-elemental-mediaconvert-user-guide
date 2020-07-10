# Using settings variables with streaming outputs<a name="using-settings-variables-with-streaming-outputs"></a>

Variables in your job settings, also called *format identifiers*, function differently for outputs in Apple HLS and DASH ISO output groups\. Here are the differences:

**For Apple HLS Outputs**  
When you use the date and time format identifiers \(`$dt$`, `$t$`, `$d$`\) in the **Segment modifier** setting, these format identifiers resolve to the completion time of each segment, rather than to the start time of the job\.

**Note**  
For jobs that use accelerated transcoding, segments might complete at the same time\. This means that date and time format identifiers don't always resolve to unique values\.

**For DASH ISO Outputs**  
You can use two additional format identifiers in the **Name modifier** setting\. These affect the DASH manifest in addition to the output file name\. Here are the identifiers:

$Number$  
In your output file names, `$Number$` resolves to a series of numbers that increment from 1\. This replaces the default, nine\-digit segment numbering in the segment file names\. For example:   
+ If you specify **video\_$Number$** for **Name modifier**, the service creates segment files named `video_1.mp4`, `video_2.mp4`, and so on\.
+ If you specify only **video\_** for **Name modifier**, the service creates segment files named `video_000000001.mp4`, `video_000000002.mp4`, and so on\.
In your DASH manifest, AWS Elemental MediaConvert includes `duration` and `startNumber` inside the `SegmentTemplate` element, like this: `<SegmentTemplate timescale="90000" media="main_video_$Number$.mp4" initialization="main_video_$Number$init.mp4" duration="3375000"/>`  
If you use the `$Number$` format identifier in an output, you must also use it in every other output of the output group\.

$Bandwidth$   
In your output file names, `$Bandwidth$` resolves to the value of **Video**, **Bitrate** plus the value of **Audio**, **Bitrate** in the output\. Regardless of whether you include this format identifier, the service uses nine\-digit segment numbering in the segment file names\.  
For example, suppose you specify these values:  
+ **Video**, **Bitrate \(bits/s\)**: **50000000** 
+  **Audio**, **Bitrate \(kbits/s\)**: **96\.0** \(96,000 bits/s\)
+ **Name modifier**: **video\_$Bandwidth$**
The value for $Bandwidth$ resolves to 50,096,000\. The service creates segment files named `video_50096000_000000001.mp4`, `video_50096000_000000002.mp4`, and so on\.  
In the manifest, AWS Elemental MediaConvert includes `duration` and `startNumber` inside the `SegmentTemplate` element, like this: `<SegmentTemplate timescale="90000" media="main_video_$Bandwidth$.mp4" initialization="main_video_$Bandwidth$init.mp4" duration="3375000"/>`\.

$Time$  
In your output file names, `$Time$` resolves to the duration, in milliseconds, of the segment\. When you include this format identifier, the service doesn't use the default nine\-digit segment numbering in the segment file names\.  
For example, if you specify **video180\_\_$Time$** for **Name modifier**, the service creates segment files named `video180__345600.mp4`, `video180__331680.mp4`, and so on\. In these examples, the segment durations are 345,600 ms and 331,680 ms\.  
In the manifest, AWS Elemental MediaConvert includes `SegmentTimeline` inside the `SegmentTemplate` element, like this:   

```
<Representation id="5" width="320" height="180" bandwidth="200000" codecs="avc1.4d400c">
        <SegmentTemplate media="video180_$Time$.mp4" initialization="videovideo180_init.mp4">
          <SegmentTimeline>
            <S t="0" d="345600" r="2"/>
            <S t="1036800" d="316800"/>
          </SegmentTimeline>
        </SegmentTemplate>
      </Representation>
```
If you use the `$Time$` format identifier in an output, you must also use it in every other output of the output group\.