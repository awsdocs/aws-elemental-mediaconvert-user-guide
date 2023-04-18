# Generating black video<a name="video-generator"></a>

This guide shows you how to generate black video with AWS Elemental MediaConvert\. To generate black video, you can add an input and include **Video generator**, or create a video output from an input that doesn't have video\.

Workflows to consider when generating black video:
+ Insert black video at the beginning of your content\.
+ Insert black video between two inputs\.
+ Insert black video at the end of your content\.
+ Create a black video track for an audio\-only or captions\-only input\.
+ Any previous combination\.

## How to generate black video<a name="w2aac12c15b9b9"></a>

In the following steps, you will include **Video generator** to generate a black video\. When you do, also specify a numerical value for **Duration** in milliseconds from `50` to `86400000`\. This creates a video input with black frames for that duration without an audio track\.

Alternatively, MediaConvert automatically creates black video when the following conditions are met: 
+ Your input doesn’t have video\. Examples include:
  + Audio\-only inputs
  + Captions\-only inputs \(in sidecar formats\)
+ Your output includes a video track\.

In the previous examples, the duration of the black video that you generate will match the duration of the input audio or captions\. 

**Generate black video by adding an input with Video generator specified\.**

1. In the **Input** pane, toggle on **Video generator**\.

1. Specify a value for **Duration** in milliseconds\.

1. After defining the rest of your job settings, choose **Create**\.

**Create a black video track for an audio\-only input\.**

1. In the **Input** pane, leave **Input file URL** blank\.

1. Under **Audio selectors**, **Audio Selector 1**, switch on **External file**\.

1. Enter the URL of your audio input\.

   1. If your input has both audio and video, MediaConvert ignores the input video\.

1. Under **Audio selectors**, specify any other required input audio settings\.

1. See [Step 3: Create output groups](specify-output-groups.md) and [Step 4: Create outputs](create-outputs.md) to set up your outputs\.

   1. You must include a video track in your output\.

   1. You must include an audio track in your output, with **Audio source** set to the **Audio selector** specified from step 2, shown previously\.

1. After defining the rest of your job settings, choose **Create**\.

1. MediaConvert automatically creates black video with the same duration as the input audio selector\.

**Create a black video track for a captions\-only input\.**

1. In the **Input** pane, leave **Input file URL** blank\.

1. Next to **Captions selectors**, choose **Add captions selector**\.

1. In **Captions Selector 1**, under **Source**, choose a sidecar captions format\.

   1. Non\-sidecar captions formats are not supported\.

1. Enter the URL of your captions input\.

1. See [Step 3: Create output groups](specify-output-groups.md) and [Step 4: Create outputs](create-outputs.md) to set up your outputs\.

   1. You must include a video track in your output\.

   1. You must include a captions track in your output, with **Captions source** set to the **Captions selector** specified from step 2 above\.

1. After defining the rest of your job settings, choose **Create**\.

1. MediaConvert automatically creates black video, with the same duration as the input **Captions selector**\.

## Video Generator FAQ<a name="w2aac12c15b9c11"></a>

**Q: What if my job generates black video and I set my output frame rate to Follow source?**

If your job does not include any other inputs, there is no input frame rate for MediaConvert to follow\. You must specify an output frame rate\.

If your job includes any other inputs with video, MediaConvert uses the frame rate from the first video input\.

**Q: What if my job generates black video I don’t define an output resolution?**

If your job does not include any other inputs, there is no input resolution for MediaConvert to follow\. Specify an output resolution\.

If your job includes any other inputs with video, MediaConvert uses the resolution from the first video input\.

## Feature restrictions for Video generator<a name="w2aac12c15b9c13"></a>

The following feature is unavailable when you generate black video:
+ Accelerated transcoding