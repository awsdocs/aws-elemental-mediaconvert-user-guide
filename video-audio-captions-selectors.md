# Including Video, Audio, and Captions in Outputs in AWS Elemental MediaConvert<a name="video-audio-captions-selectors"></a>

You use *selectors* to specify whether information \(video, audio, or captions\) from your input file is included in a given output\. A selector is a construct that AWS Elemental MediaConvert uses to group together data from the input\. For example, you might put some, but not all, of an input asset's audio tracks into an audio selector\.

## Creating Selectors \(Input\)<a name="create-selectors"></a>

When you set up your input, you can create audio and captions selectors\. To do that, you specify audio tracks and captions that are in your input and provide some basic information about them\. For more information, see [Specify Input Settings](setting-up-a-job.md#specify-input-settings)\. 

You don't need to create a video selector because AWS Elemental MediaConvert automatically generates a video selector based on the video stream in your input\. However, you must provide values for the fields of the existing video selector\. AWS Elemental MediaConvert doesn't support inputs with multiple video streams, such as Quad 4k\.

## Using Selectors \(Outputs\)<a name="add-selectors-to-output"></a>

When you set up your outputs, you use selectors to specify the elements \(video, audio, or captions\) from your input to include in each output\. An output might or might not include each type of selector\. For example, you might create an audio\-only output as a standalone file\. Or you might create several outputs with the same video, audio, and captions streams for an ABR stack\. \(In that case, you likely would apply different settings to the same video in the different outputs\.\)

### Outputs as Standalone Files \(File Group\)<a name="add-selectors-file-outputs"></a>

Standalone file outputs are part of a file group output group\. For each element \(video, audio, or captions\) that you specify by using a selector, AWS Elemental MediaConvert includes content in the file that it creates\. Settings that you specify in one output for handling a selected element don't apply to that element in other outputs\.

### Outputs in an ABR Stack \(HLS, DASH, Smooth Groups\)<a name="add-selectors-ABR-outputs"></a>

ABR outputs are part of an HLS, DASH, or Smooth output group\. Except in unusual cases, you set up your ABR output group with a separate output for each element in your ABR stack\. That is, one output per video resolution, one output per audio track, and one output per captions language\. You specify each video, audio, or captions element to include in the output by using a selector\. 

In the following illustration, each orange box represents an output within the output group\. 

![\[Each rendition in an ABR stack has its own output in the output group.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/ABRsegSeparately.png)