# Adjusting the Output Timecode Settings<a name="timecode-output"></a>

There are two timecode\-related settings that you can adjust differently for each output\. These are **Timecode insertion** and **Timecode burn\-in**\.

## Inserting Timecode Metadata<a name="timecode-insertion"></a>

The **Timecode insertion** setting determines whether a given output has timecodes embedded in its metadata\. AWS Elemental MediaConvert automatically puts this information in the appropriate place, depending on the output codec\. For MPEG\-2 and QuickTime codecs, such as Apple ProRes, the service inserts the timecodes in the video I\-frame metadata\. For H\.265 \(HEVC\) and H\.264 \(AVC\), the service inserts the timecodes in the supplemental enhancement information \(SEI\) picture timing message\. 

**To include timecode metadata in an output**

1. On the **Create job** page, in the **Job** pane on the left, choose an output\.

1. Under **Stream settings**, **Timecode insertion**, choose **PIC\_TIMING\_SEI** to include timecode metadata\. Choose **Disabled** to leave out timecode metadata\.

If you use the API or an SDK, you can find this setting in the JSON file of your job, called `TimecodeInsertion`, located in `Settings`, `OutputGroups`, `Outputs`, `VideoDescription`\.

## Burning In Timecodes on the Video Frames<a name="timecode-burn-in"></a>

The **Timecode burn\-in** setting determines whether a given output has visible timecodes inscribed into the video frames themselves\. The timecodes are not an overlay, but rather a permanent part of the video frames\.

**To burn in timecodes in an output**

1. On the **Create job** page, in the **Job** pane on the left, choose an output\.

1. Under **Stream settings**, **Preprocessors**, choose **Timecode burn\-in**\.

1. Optionally, provide values for the **Prefix**, **Font size**, and **Position** settings\. Even if you don't provide these values, timecodes are burned into your output using these default values: 

   + **Prefix**: no prefix

   + **Font size**: **Extra Small \(10\)**

   + **Position**: **Top Center**

   For details about each of these settings, choose the **Info** link next to **Timecode burn\-in**\.

If you use the API or an SDK, you can find these settings in the JSON file of your job\. These settings are under `Settings`, `OutputGroups`, `Outputs`, `VideoDescription`, `VideoPreprocessors`, `TimecodeBurnin`\.