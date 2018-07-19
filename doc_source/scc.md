# SCC, SRT, STL, TTML \(Sidecar\)<a name="scc"></a>

SCC, SRT, STL, and TTML are sidecar captions formats\. With these formats, you provide input captions as a separate file\. AWS Elemental MediaConvert handles all sidecar formats the same way\. The service can pass them through to the output in the same format or convert them into another sidecar format\. In all cases, you must create one captions selector for the entire set of captions languages\.

Provide the following values for the captions selector fields:
+ **External captions file**: The URI to the captions file\. AWS Elemental MediaConvert accepts captions files from Amazon S3\.
+ **Time delta**: \(Optional\) Use this setting if you need to adjust the sync between the captions and the video:
  + Type a positive number to add to the times in the captions file\. For example, type **15** to add 15 seconds to all the times in the captions file\.
  + Type a negative number to subtract from the times in the captions file\. For example, type **\-5** to subtract 5 seconds from the times in the captions file\.

    The format of the times in the captions file doesn't have to match the value in the **Timecode config** field \(in the input portion of your job\)\. The number that you type in this field simply delays the captions or makes the captions play earlier, regardless of the timecode formats\.

**Note**  
To make sure that your captions are properly synchronized with your video, check that the value for **Timecode source** in the **Video selector** section matches the timecodes in your captions file\. For example, if the timecodes in your captions file start at zero but your video has embedded timecodes starting at 01:00:00:00, change the default value for **Timecode source** from **Embedded** to **Start at 0**\.  
If you use the API or an SDK, you can find this setting in the JSON file of your job, called `TimecodeSource`, located in `Settings`, `Inputs`\. When you use SCC, you must provide a value for `TimecodeSource`\. Otherwise, AWS Elemental MediaConvert will not insert the captions\. 

## Use Cases for Time Delta<a name="time-delta-use-cases"></a>

**SCC**: The start time for the captions is not 00:00:00:00\. For captions handling, AWS Elemental MediaConvert always treats the video and audio start time as 00:00:00, even if your input video file has embedded timecodes that start at a time other than 00:00:00:00\. If your captions file assumes a start time other than 00:00:00, you might need to adjust the captions start time\. 

For example, your video file may have embedded timecodes that start at 00:05:00:00 and the first instance of dialogue that requires captions might be one minute into the video, at timecode 00:06:00:00\. If your captions file is set to begin captions at 00:06:00:00, you must subtract five minutes from the captions\. In this case, you would enter **\-300** in the **Time delta** field\.

**SRT, STL, TTML**: The start time in the captions file is slightly off\. With these types of captions files, the start time for both the video file \(containing video and audio\) and the captions file is always 00:00:00\.

For example, the first instance of dialogue that requires captions might be at 00:06:15\. But in the captions file, this time is marked as 00:06:18 and every other instance of captions is also off by 3 seconds\. The solution is to subtract three seconds from the captions file\. In this case, you would enter "\-3" in the **Time delta** field\.