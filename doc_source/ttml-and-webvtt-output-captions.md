# IMSC, TTML, and WebVTT \(sidecar\) output captions<a name="ttml-and-webvtt-output-captions"></a>

If your output captions are IMSC, TTML or WebVTT format, set them up in your outputs according to the following information\. For restrictions on IMSC support, see [IMSC captions support in AWS Elemental MediaConvert](imsc-captions-support.md)\.

## Where to specify the captions<a name="where-ttml-and-webvtt-output-captions"></a>

Put your captions in the same output group, but a different output from your video\.

After you add captions to an output, delete the **Video** and **Audio 1** groups of settings that the service automatically created with the output\.

**To delete the Video and Audio 1 groups of settings**

1. On the **Create job** page, in the **Job** pane on the left, under **Output groups**, choose the output that contains the groups of settings that you want to delete\.

1. The **Video** group of settings is automatically displayed in the **Stream settings** section\. Choose the **Remove video selector** button\.

1. The **Audio 1** group of settings is automatically displayed in the **Stream settings** section\. Choose the **Remove** button\.

## How to specify multiple captions tracks<a name="multilang-ttml-and-webvtt-output-captions"></a>

Put each captions track in its own output\.

**Note**  
The captions track that you specify first in your job is signaled as the default track in the HLS manifest\.

## Sidecar captions container options<a name="sidecar-captions-container-options"></a>

Depending on your output group, you can choose the captions container for IMSC and TTML captions outputs\.

For **DASH ISO** output groups, you can choose from these:
+ Fragmented MP4 \(`.fmp4`\)
+ Raw \(`.xml` for IMSC, `.ttml` for TTML\)

For all other output groups, IMSC and TTML files are raw\.

**To specify the captions container for IMSC and TTML captions in DASH ISO output groups**

1. Set up the outputs in your **DASH ISO** output group as described in [Creating outputs in ABR streaming output groups](create-outputs-in-abr-streaming-output-groups.md)\. Put captions in a separate output\.

1. On the **Create job** page, in the **Job** pane on the left, choose the captions output\.

1. In the **Output settings** section on the right, choose **Container settings**, and then enable **DASH container settings**\.

1. For **Captions container**, keep the default **Raw** or choose **Fragmented MPEG\-4**\.