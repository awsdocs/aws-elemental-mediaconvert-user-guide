# Putting timecodes in your outputs<a name="timecode-output"></a>

There are two timecode\-related settings that you can adjust differently for each output: **Timecode insertion** and **Timecode burn\-in**\.

## Inserting timecode metadata<a name="timecode-insertion"></a>

The **Timecode insertion** setting determines whether a given output has timecodes embedded in its metadata\. MediaConvert automatically puts this information in the appropriate place, depending on the output codec\. For MPEG\-2 and QuickTime codecs, such as Apple ProRes, the service inserts the timecodes in the video I\-frame metadata\. For H\.265 \(HEVC\) and H\.264 \(AVC\), the service inserts the timecodes in the supplemental enhancement information \(SEI\) picture timing message\. 

**To include timecode metadata in an output \(console\)**

1. On the **Create job** page, in the **Job** pane on the left, choose an output\.

1. Under **Stream settings**, **Timecode insertion**, choose **Insert** to include timecode metadata\. Choose **Disabled** to omit timecode metadata\.

**To include timecode metadata in an output \(API, SDK, and AWS CLI\)**
+ In your JSON job specification, set a value for [TimecodeInsertion](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-videodescription-timecodeinsertion), located in `Settings`, `OutputGroups`, `Outputs`, `VideoDescription`\.

  Use `PIC_TIMING_SEI` to include timecode metadata\. Use `DISABLED` to omit timecode metadata\.

## Burning in timecodes on the video frames<a name="timecode-burn-in"></a>

The **Timecode burn\-in** setting determines whether a given output has visible timecodes inscribed into the video frames themselves\. The timecodes are not an overlay, but rather a permanent part of the video frames\.

**To burn in timecodes in an output \(console\)**

1. On the **Create job** page, in the **Job** pane on the left, choose an output\.

1. Under **Stream settings**, **Preprocessors**, choose **Timecode burn\-in**\.

1. Optionally, provide values for the **Prefix**, **Font size**, and **Position** settings\. Even if you don't provide these values, timecodes are burned into your output using these default values: 
   + **Prefix**: no prefix
   + **Font size**: **Extra Small \(10\)**
   + **Position**: **Top Center**

   For details about each of these settings, choose the **Info** link next to **Timecode burn\-in**\.

**To burn in timecodes in an output \(API, SDK, and AWS CLI\)**

1. In your JSON job specification, include the setting [TimecodeBurnin](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-videopreprocessor-timecodeburnin)\. `TimecodeBurnin` is located in `Settings`, `OutputGroups`, `Outputs`, `VideoDescription`, `VideoPreprocessors`\.

1. Optionally, provide values for the settings that are children of `TimecodeBurnin`\. If you don't provide these values, timecodes are burned into your output using these default values: 
   + `Prefix`: *no prefix*
   + `FontSize`: `10`
   + `Position`: `TOP_CENTER`