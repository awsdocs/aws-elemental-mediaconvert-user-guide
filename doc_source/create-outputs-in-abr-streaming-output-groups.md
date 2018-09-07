# Creating Outputs in ABR Streaming Output Groups<a name="create-outputs-in-abr-streaming-output-groups"></a>

For each ABR streaming output group that you set up in [Step 3: Create Output Groups](specify-output-groups.md), create and set up an output for each media element that you want in the ABR streaming package, as shown in the following illustration\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/Job_outputs-ABR.png)

## Creating Video ABR Streaming Outputs<a name="video-abr-streaming-outputs"></a>

For each video output that you include in your output group, MediaConvert creates one video rendition, or set of segmented video files\. Multiple video renditions in a streaming package, of varying resolutions and video quality, allow the end viewer's device to adapt the quality of video to the available bandwidth\.

**Note**  
Although the job has only one video *input* selector, ABR streaming output groups often have several video *outputs* per output group\. 

**To create and set up video ABR streaming outputs**

1. On the **Create job** page, in the **Job** pane on the left, under **Output Groups**, below the **CMAF**, **Apple HLS**, **DASH ISO**, or **Microsoft Smooth Streaming** output group that you want add outputs to, choose **Output 1**\. 

   When you create an output group, MediaConvert automatically populates the output group with output 1, so you don't need to explicitly create the first output\.

1. In the **Output settings** pane, for **Name modifier**, type a value\.

   MediaConvert appends the name modifier to the file names that it assigns to the files that it creates for this output\. Type a name modifier that will make it easy to identify which files came from which output, such as `-video-hi-res`\.

1. If one of the predefined groups of settings listed under **Preset** is suitable for your workflow, choose it from the list\. If you use a preset, skip the next step of this procedure\.

1. Specify your video settings as follows:

   1. In the **Output settings** section, specify values for any remaining general settings\. Depending on the output group type, these settings might include transport stream settings or other container settings\. For more information about individual settings, choose the **Info** links on the console\.

   1. In the **Stream settings** section, specify values for video encoding\. The video settings are selected by default, so you don't need to explicitly choose this group of settings\. For more information about individual settings, choose the **Info** links on the console\.
**Note**  
There is only one input video selector per job, so you don't need to explicitly choose it when you set up your video outputs\.

   For more information about individual settings, choose the **Info** links on the console\.

1. If your output includes a group of audio settings by default, delete it as follows:

   1. In the **Stream settings** section, choose **Audio 1**\.

   1. Choose **Remove audio**\.

1. If you want multiple video renditions in your ABR streaming package, repeat the preceding steps of this procedure to create an additional video output for each one\.

## Creating Audio ABR Streaming Outputs<a name="audio-abr-streaming-outputs"></a>

For each audio output you include in your output group, MediaConvert will create one audio rendition, or set of segmented video files\. The most common reason to include multiple audio renditions is to provide multiple language options\. If you are only providing a single language, you will probably only need one audio output\.

**To create and set up audio ABR streaming outputs**

1. Create an output for your first audio track\. Usually an audio track corresponds to one language\.
**Note**  
If you are working in a CMAF output group, skip this step\. The first audio output is created for you\.

   1. In the **Job** pane, choose the output group that you're working in\.

   1. In the **Outputs** pane, choose **Add output**\. 

   1. Choose the output that you just created\.

   1. If your output includes a group of video settings by default, choose **Remove video** to delete it\. This leaves the **Audio 1** group of settings displayed\.

1. In the **Output settings** pane, for **Name modifier**, type a value\.

   MediaConvert appends the name modifier to the file names that it assigns to the files that it creates for this output\. Type a name modifier that will make it easy to identify which files came from which output, such as `-audio-english`\.

1. If one of the predefined groups of settings listed under **Preset** is suitable for your workflow, choose it from the list\. If you use a preset, skip the next step of this procedure\.

1. Specify your audio settings as follows:

   1. In the **Output settings** section, specify values for any remaining general settings\. For more information about individual settings, choose the **Info** links on the console\.

   1. Under **Stream settings**, for **Audio source**, choose one of the audio selectors that you created in [Step 2: Create Input Selectors for Video, Audio, and Captions](create-selectors.md)\.

   1. In the **Stream settings** section, specify values for audio encoding\. For more information about individual settings, choose the **Info** links on the console\.

1. If you have additional audio assets to include in the ABR streaming package, create an output for each of them as follows:

   1. In the **Job** pane, choose the output group that you're working in\.

   1. In the **Outputs** pane, choose **Add output**\. 

   1. Choose the output that you just created\.

   1. If your output includes a group of video settings by default, choose **Remove video** to delete it\. This leaves the **Audio 1** group of settings displayed\.

   1. Set up the output as described in steps 2 through 4 of this procedure\.

## Creating Captions ABR Streaming Outputs<a name="captions-abr-streaming-outputs"></a>

Setting up captions can be complex\. For detailed information, see [Setting Up Captions in AWS Elemental MediaConvert Jobs](including-captions.md)\. For basic instructions, complete the following procedure\.

**To create and set up captions ABR streaming outputs**

1. Create an output for your first set of captions\. Usually a set of captions corresponds to one language\.

   1. In the **Job** pane, choose the output group that you're working in\.

   1. In the **Outputs** pane, choose **Add output**\. 

   1. Choose the output that you just created\.

   1. If your output includes groups of video and audio settings by default, choose **Remove video** and **Remove audio** to delete them\. 

   1. Choose **Add captions** to display a set of captions settings\.

1. In the **Output settings** pane, for **Name modifier**, type a value\.

   MediaConvert appends the name modifier to the filenames it assigns to the files it creates for this output\. Type a name modifier that will make it easy to identify which files came from which output, such as `-captions-english`\.

1. Specify your captions settings as follows:

   1. In the **Output settings** section, specify values for any remaining general settings\. For more information about individual settings, choose the **Info** links on the console\.

   1. Under **Stream settings**, for **Captions source**, choose one of the captions selectors that you created in [Step 2: Create Input Selectors for Video, Audio, and Captions](create-selectors.md)\.

   1. In the **Stream settings** section, specify values for the remaining captions settings\. 