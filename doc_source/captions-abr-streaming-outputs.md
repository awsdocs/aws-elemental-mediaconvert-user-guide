# Creating captions ABR streaming outputs<a name="captions-abr-streaming-outputs"></a>

Setting up captions can be complex\. For detailed information, see [Setting up captions in MediaConvert jobs](including-captions.md)\. For basic instructions, complete the following procedure\.

**To create and set up captions ABR streaming outputs**

1. Create an output for your first set of captions\. Usually a set of captions corresponds to one language\.

   1. In the **Job** pane, choose the output group that you're working in\.

   1. In the **Outputs** pane, choose **Add output**\. 

   1. Choose the output that you just created\.

   1. If your output includes groups of video and audio settings by default, choose **Remove video** and **Remove audio** to delete them\. 

   1. Choose **Add captions** to display a set of captions settings\.

1. In the **Output settings** pane, for **Name modifier**, enter a value\.

   AWS Elemental MediaConvert appends the name modifier to the file names that it assigns to the files it creates for this output\. Enter a name modifier that will make it easy to identify which files came from which output, such as `-captions-english`\.

1. Specify your captions settings as follows:

   1. In the **Output settings** section, specify values for any remaining general settings\. For more information about individual settings, choose the **Info** link next to each setting\.

   1. Under **Stream settings**, for **Captions source**, choose one of the captions selectors that you created in [Step 2: Create input selectors for video, audio, and captions](create-selectors.md)\.

   1. In the **Stream settings** section, specify values for the remaining captions settings\. 