# Creating video ABR streaming outputs<a name="video-abr-streaming-outputs"></a>

For each video output that you include in your output group, AWS Elemental MediaConvert creates one video rendition, or set of segmented video files\. Multiple video renditions in a streaming package, of varying resolutions and video quality, allow the end viewer's device to adapt the quality of video to the available bandwidth\.

**Note**  
Although the job has only one video *input* selector, ABR streaming output groups often have several video *outputs* per output group\. 

**To create and set up video ABR streaming outputs**

1. On the **Create job** page, in the **Job** pane on the left, under **Output Groups**, below the **CMAF**, **Apple HLS**, **DASH ISO**, or **Microsoft Smooth Streaming** output group that you want add outputs to, choose **Output 1**\. 

   When you create an output group, AWS Elemental MediaConvert automatically populates the output group with output 1, so you don't need to explicitly create the first output\.

1. In the **Output settings** pane, for **Name modifier**, enter a value\.

   AWS Elemental MediaConvert appends the name modifier to the file names that it assigns to the files that it creates for this output\. Enter a name modifier that will make it easy to identify which files came from which output, such as `-video-hi-res`\.

1. If one of the predefined groups of settings listed under **Preset** is suitable for your workflow, choose it from the list\. If you use a preset, skip the next step of this procedure\.

1. Specify your video settings as follows:

   1. In the **Output settings** section, specify values for any remaining general settings\. Depending on the output group type, these settings might include transport stream settings or other container settings\. For more information about individual settings, choose the **Info** link next to each setting\.

   1. In the **Stream settings** section, specify values for video encoding\. The video settings are selected by default, so you don't need to explicitly choose this group of settings\. For more information about individual settings, choose the **Info** link next to each setting\.
**Note**  
There is only one input video selector per job, so you don't need to explicitly choose it when you set up your video outputs\.

   For more information about individual settings, choose the **Info** links on the console\.

1. If your output includes a group of audio settings by default, delete it as follows:

   1. In the **Stream settings** section, choose **Audio 1**\.

   1. Choose **Remove audio**\.

1. If you want multiple video renditions in your ABR streaming package, repeat the preceding steps of this procedure to create an additional video output for each one\.