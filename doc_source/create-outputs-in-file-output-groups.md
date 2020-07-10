# Creating and setting up outputs in File output groups<a name="create-outputs-in-file-output-groups"></a>

With **File** output groups, each asset that the service creates corresponds to one output, rather than one output group\. Each asset contains all video, audio, and captions elements\. Therefore, it's simplest to set up by first creating the output, and then setting up all the output selectors\. 

## Create File outputs<a name="create-file-outputs"></a>

If you created a **File** output group in [Step 3: Create output groups](specify-output-groups.md), create and set up an output in the file output group for each standalone file that you intend to create, as shown in the following illustration\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/Job_outputs-file.png)

**To create an output in a File output group**

1. When you create an output group, AWS Elemental MediaConvert automatically populates the output group with output 1, so you don't need to explicitly create it\. If you are creating only one standalone file, skip the rest of this procedure\.

1. If you want to create more than one standalone file, create additional outputs as follows:

   1. On the **Create job** page, in the **Job** pane on the left, under **Output Groups**, choose **File group**\.

   1. In the **Outputs** pane, choose **Add output**\.

## Set up output selectors in File outputs<a name="set-up-output-selectors-in-file-outputs"></a>

Next, for each **File** output you just created, set up output selectors\. The following illustration shows the three types of output selectors, all contained in one output\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/Job_output-selectors-file.png)

**To set up output selectors in a File output**

1. On the **Create job** page, in the **Job** pane on the left, under **Output Groups**, under **File group**, choose **Output 1**\. 

1. In the **Output settings** pane, for **Name modifier**, enter a value\.

   AWS Elemental MediaConvert appends the name modifier to the file names that it assigns to the file that it creates for this output\. Enter a name modifier that will make it easy to identify which files came from which output, such as `-standalone-hi-res`\.

1. If one of the predefined groups of settings listed under **Preset** is suitable for your workflow, choose it from the list\. If you use a preset, skip the next step of this procedure\.
**Note**  
Output presets can contain up to one set each of video, audio, and captions settings\. Therefore, if your standalone output file contains more than one audio or captions asset, you can't use a preset\.  
If you can't use presets in your output, but you want to use the preset settings as a starting point, choose the preset, then choose **No preset** from the **Preset** dropdown list\. This prepopulates your output with the same settings that are in the preset\.

1. Specify your output settings as follows:

   1. In the **Output settings** section, specify values for any remaining general settings\. These settings vary depending on the container that you choose\. For more information about individual settings, choose the **Info** link next to each setting\.

   1. In the **Stream settings** section, specify values for video encoding\. For more information about individual settings, choose the **Info** link next to each setting\.
**Note**  
The video settings tab is selected by default, so you don't need to explicitly choose this group of settings\. 
**Note**  
There is only one input video selector per job, so you don't need to explicitly choose it when you set up your video outputs\.

   1. Choose **Audio 1** to display the group of encoding settings for the first audio asset\. **Audio 1** is located on the left side of the **Stream settings** pane, below **Video**\.

   1. Under **Stream settings**, for **Audio source**, choose one of the audio selectors that you created in [Step 2: Create input selectors for video, audio, and captions](create-selectors.md)\.

   1. In the **Stream settings** section, specify values for audio encoding\. For more information about individual settings, choose the **Info** link next to each setting\.

   1. To include captions in the output, choose **Add captions** to display a group of captions settings\. For more information about setting up captions, see [Setting up captions in MediaConvert jobs](including-captions.md)\.