# Creating audio ABR streaming outputs<a name="audio-abr-streaming-outputs"></a>

For each audio output that you include in your output group, AWS Elemental MediaConvert creates one audio rendition, or set of segmented video files\. The most common reason to include multiple audio renditions is to provide multiple language options\. If you provide only one language, you probably need only one audio output\.

**Note**  
For AAC streaming outputs, the initial segment is longer in duration than the others\. This is because, with AAC, the initial segment must contain silent AAC pre\-roll samples before the audible part of the segment\. MediaConvert accounts for these extra samples in the timestamps, so the audio plays back correctly\. 

**To create and set up audio ABR streaming outputs**

1. Create an output for your first audio track\. Usually an audio track corresponds to one language\.
**Note**  
If you are working in a CMAF output group, skip this step\. The first audio output is created for you\.

   1. In the **Job** pane, choose the output group that you're working in\.

   1. In the **Outputs** pane, choose **Add output**\. 

   1. Choose the output that you just created\.

   1. If your output includes a group of video settings by default, choose **Remove video** to delete it\. This leaves the **Audio 1** group of settings displayed\.

1. In the **Output settings** pane, for **Name modifier**, enter a value\.

   AWS Elemental MediaConvert appends the name modifier to the file names that it assigns to the files that it creates for this output\. Enter a name modifier that will make it easy to identify which files came from which output, such as `-audio-english`\.

1. If one of the predefined groups of settings listed under **Preset** is suitable for your workflow, choose it from the list\. If you use a preset, skip the next step of this procedure\.

1. Specify your audio settings as follows:

   1. In the **Output settings** section, specify values for any remaining general settings\. For more information about individual settings, choose the **Info** link next to each setting\.

   1. Under **Stream settings**, for **Audio source**, choose one of the audio selectors that you created in [Step 2: Create input selectors for video, audio, and captions](create-selectors.md)\.

   1. In the **Stream settings** section, specify values for audio encoding\. For more information about individual settings, choose the **Info** link next to each setting\.

1. If you have additional audio assets to include in the ABR streaming package, create an output for each of them as follows:

   1. In the **Job** pane, choose the output group that you're working in\.

   1. In the **Outputs** pane, choose **Add output**\. 

   1. Choose the output that you just created\.

   1. If your output includes a group of video settings by default, choose **Remove video** to delete it\. This leaves the **Audio 1** group of settings displayed\.

   1. Set up the output as described in steps 2 through 4 of this procedure\.