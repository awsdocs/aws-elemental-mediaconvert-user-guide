# Adjusting the output timeline with the job\-wide timecode configuration<a name="timecode-jobconfig"></a>

The values that you specify for the job\-wide **Timecode configuration** settings affect the output timeline\. For information about which features are affected by the output timeline, see [Output timeline ](output-timeline.md)\.

**To adjust the job\-wide timecode configuration \(console\)**

1. On the **Create job** page, in the **Job** pane on the left, choose **Settings**\.

1.  In the **Timecode configuration** section, for **Source**, choose one of the following values:
   + **Embedded**: The service uses any timecodes that are embedded in the video\.
   + **Start at 0**: The service ignores any embedded timecodes and assigns the first video frame the timecode 00:00:00:00 \(HH:MM:SS:FF\)\.
   + **Specified start**: The service ignores any embedded timecodes and assigns the first video frame the value that you provide for **Start Timecode**\. 

     The **Start Timecode** field appears when you choose **Specified start**\.

   If you use the API or an SDK, you can find this setting in the JSON file of your job\. The setting name is `Source`, located inside `Settings`, `TimecodeConfig`\.

   If you don't choose a value for **Source**, the service defaults to **Embedded**\.
**Note**  
If your input video doesn't have embedded timecodes and you set **Source** to **Embedded** or leave **Source** unspecified, your output won't have timecodes\. This means that features that require a timecode\-based start time, such as sidecar captions and graphic overlays, won't appear in your output\.

1. Set a value for **Anchor Timecode**\.

   If you use an editing platform that relies on an anchor timecode, use **Anchor timecode** to specify a point at which the input and output frames have the same timecode\. Use the following 24\-hour format with a frame number: HH:MM:SS:FF\. This setting ignores frame rate conversion\.

   The system behavior for **Anchor timecode** varies depending on your setting for **Source**:
   + If you choose **Start at 0** for **Source**, the anchor frame is the timecode that you provide in **Anchor timecode**, counting from 00:00:00:00\. 

     For example, if you set **Anchor timecode** to 01:00:05:00, the anchor frame is one hour and five seconds into the video\.
   + If you choose **Embedded** for **Source**, the anchor frame is the timecode that you provide in **Anchor timecode**, counting from the first embedded timecode\. 

     For example, if your embedded timecodes start at 01:00:00:00 and you set **Anchor timecode** to 01:00:05:00, the anchor frame is five seconds into the video\.
   + If you choose **Specified start** for **Source**, the anchor frame is the timecode that you provide in **Anchor timecode**, counting from the timecode that you specify for the first frame\.

     For example, if you specify 00:30:00:00 as your start timecode and you set **Anchor timecode** to 01:00:05:00, the anchor frame is thirty minutes and five seconds into the video\.

   If you use the API or an SDK, you can find this setting in the JSON file of your job\. The setting name is `Anchor`, located in `Settings`, `TimecodeConfig`\.

   If you don't set a value for **Anchor timecode**, the service doesn't use any anchor timecode\.

1. Under **Timestamp offset**, provide a date\. This setting applies only to outputs that support a program\-date\-time stamp\. Use **Timestamp offset** to overwrite the timecode date without affecting the time and frame number\. This setting has no effect unless you also include the program\-date\-time stamp in the output\.

   If you use the API or an SDK, you can find this setting in the JSON file of your job\. The setting name is `TimestampOffset`, located in `Settings`, `TimecodeConfig`\.

**To adjust the job\-wide timecode configuration \(API, SDK, and AWS CLI\)**

1. In your JSON job specification, set a value for [Source](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-timecodeconfig-source), located inside `Settings`, `TimecodeConfig`\. Choose one of the following values:
   + **EMBEDDED**: The service uses any timecodes that are embedded in the video\.
   + **ZEROBASED**: The service ignores any embedded timecodes and assigns the first video frame the timecode 00:00:00:00 \(HH:MM:SS:FF\)\.
   + **SPECIFIEDSTART**: The service ignores any embedded timecodes and assigns the first video frame the value that you provide for **Start Timecode**\. 

     The **Start Timecode** field appears when you choose **Specified start**\.

   If you don't choose a value for **Source**, the service defaults to **Embedded**\.
**Note**  
If your input video doesn't have embedded timecodes and you set **Source** to **Embedded** or leave **Source** unspecified, your output won't have timecodes\. This means that features that require a timecode\-based start time, such as sidecar captions and graphic overlays, won't appear in your output\.

1. Optional\. In your JSON job specification, set a value for `Anchor`, located in `Settings`, `TimecodeConfig`\.

   If you use an editing platform that relies on an anchor timecode, use `Anchor` to specify a point at which the input and output frames have the same timecode\. Use the following 24\-hour format with a frame number: HH:MM:SS:FF\. This setting ignores frame rate conversion\.

   The system behavior for `Anchor` varies depending on your setting for `Source`:
   + If you choose `ZEROBASED` for `Source`, the anchor frame is the timecode that you provide in `Anchor`, counting from 00:00:00:00\. 

     For example, if you set `Anchor` to 01:00:05:00, the anchor frame is one hour and five seconds into the video\.
   + If you choose `EMBEDDED` for `Source`, the anchor frame is the timecode that you provide in `Anchor`, counting from the first embedded timecode\. 

     For example, if your embedded timecodes start at 01:00:00:00 and you set `Anchor` to 01:00:05:00, the anchor frame is five seconds into the video\.
   + If you choose `SPECIFIEDSTART` for `Source`, the anchor frame is the timecode that you provide in `Anchor`, counting from the timecode that you specify for the first frame\.

     For example, if you specify 00:30:00:00 as your start timecode and you set `Anchor` to 01:00:05:00, the anchor frame is thirty minutes and five seconds into the video\.

1. Optional\. In your JSON job specification, set a value for `TimestampOffset`, located in `Settings`, `TimecodeConfig`\. Specify the date in the following format: `YYYY-MM-DD`\. For example, `2008-06-26`\.

   This setting applies only to outputs that support a program\-date\-time stamp\. Use **Timestamp offset** to overwrite the timecode date without affecting the time and frame number\. This setting has no effect unless you also include the program\-date\-time stamp in the output\.