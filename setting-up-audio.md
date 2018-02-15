# Setting Up Audio in AWS Elemental MediaConvert Jobs<a name="setting-up-audio"></a>

To set up your audio without changing the channels in your tracks, follow the basic steps described in this topic\. 

For workflows that require channel\-level control, use the audio channel remix feature, which supports the following workflows:

+ Changing the order of channels in an audio track

+ Moving audio channels from one or more input tracks to different output tracks

+ Combining the audio from multiple channels into a single channel

+ Splitting the audio from a single channel into multiple channels

+ Adjusting the loudness level of audio channels

## Create Input Audio Selectors<a name="create-input-audio-selectors"></a>

When you set up audio, you begin by creating audio selectors\. Audio selectors identify a particular audio track or set of tracks from the input\. When you set up an output to include audio, you do so by specifying audio selectors\.

**To create input audio selectors**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create job**\. 

1. Under **Audio selectors**, under **Selector type**, choose the identifier \(track, PID, or language code\) that you use to pick the track or set of tracks for this selector\. 

1. In the field under **Selector type**, specify the track or tracks that you want the encoding service to associate with the selector\. You can provide a single value or a comma\-separated list of values\. You can also use a wildcard \(\*\) instead of a track number\.

   For information about the other settings that are available for input audio selectors, choose the **Info** link next to a setting\.

1. Create more selectors as necessary\. To do so, in the left pane of the **Create new job** page, under **Audio selectors**, choose **Add audio selector** and then specify the tracks that the service will associate with the selector\.

## Set Up Audio in Outputs<a name="set-up-audio-in-outputs"></a>

You include audio in your outputs by choosing an audio selector\.  Create audio selectors before you set up audio in your outputs\.

**To set up audio for each output**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Follow the steps in Create input audio selectors, and then return to step 3 in this procedure\.

1. Set up your input, output groups, and outputs for video and audio, as described in [Setting Up a Job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring Complex Jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\.

1. In the left pane, choose the appropriate output from the list of outputs\.

1. Under **Encoding settings**, choose **Audio 1**\. This displays an audio settings area\.

1. Under **Audio source**, choose an audio selector\. This identifies an audio track or set of tracks from the input to include in this output\.

1. Choose how you want the audio encoded for the output\. For details about each setting, choose the **Info** link next to the setting\.

1. Repeat steps 4 through 7 for each output\.