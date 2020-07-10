# Using Dolby Atmos encoding with AWS Elemental MediaConvert<a name="using-dolby-atmos-encoding"></a>

AWS Elemental MediaConvert can encode Dolby Digital Plus with Atmos channel\-based, immersive audio input channels\.

**Note**  
Understanding Dolby Atmos is required prerequisite knowledge for using this feature\. Your input audio channels must already be set up as 16 mono PCM channels intended for Dolby Atmos playback\. For more information about Dolby Atmos, see the Dolby online documentation\.

## Input File Requirements for Dolby Atmos Encoding<a name="input-file-requirements-for-dolby-atmos-encoding"></a>

 To encode Dolby Atmos, you must have 16 input channels of PCM audio, either in individual \.wav files or as tracks in a single container\.

**Note**  
AWS Elemental MediaConvert doesn't support ADM or DAMF input\.

## Feature Restrictions for Dolby Atmos Encoding<a name="feature-restrictions-for-dolby-atmos-encoding"></a>

Note the following restrictions in the AWS Elemental MediaConvert implementation of Dolby Atmos encoding:
+ **Channel\-based immersive only:** AWS Elemental MediaConvert supports only channel\-based immersive \(CBI\) content\. MediaConvert doesn't read any Atmos metadata in the input audio files or in sidecar metadata files\. 
+ **Output codec:** You can create Dolby Atmos audio outputs encoded with only the Dolby Digital Plus \(EAC3\) codec\.
+ **Output containers:** For file outputs, you can create Dolby Atmos audio in only in one of the video containers that supports Dolby Digital Plus: MPEG\-4, MPEG\-2 Transport Stream, or QuickTime\.
+ **Output packages:** For adaptive bitrate \(ABR\) outputs, you can create Dolby Atmos audio in any of the AWS Elemental MediaConvert output group types: CMAF, Apple HLS, DASH ISO, or Microsoft Smooth Streaming\.

## Setting up a job for Dolby Atmos encoding<a name="setting-up-a-job-for-dolby-atmos-encoding"></a>

To encode Dolby Atmos, provide 16 input channels of PCM audio, either in individual \.wav files or as tracks in a single container\.

If you provide input audio as individual \.wav files, you specify them in order in your input\. You specify them as **Audio selector 1**, **Audio selector 2**, and so on, up to **Audio selector 16**\. If you provide your audio as a single file containing 16 tracks, you specify the file in your input as **Audio selector 1**, and then you specify the tracks individually within that audio selector\. 

**Important**  
Regardless of whether they are in separate files or a single file, you must set up the channels in the following order: L, R, C, LFE, Ls, Rs, Lrs, Rrs, Lw, Rw, Ltf, Rtf, Ltm, Rtm, Ltr, Rtr\.

For more details about setting up your job for Dolby Atmos encoding, see one of the following procedures:

[Procedure with separate audio input files](#proc-atmos-separate-input-files)

[Procedure with a single audio input file](#proc-atmos-single-input-file)

**To set up a Dolby Atmos job, with audio inputs as 16 individual \.wav files**<a name="proc-atmos-separate-input-files"></a>

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create job**\.

1. Set up your input video as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. Set up your input audio selectors as follows:

   1. On the **Create job** page, in the **Job** pane on the left, choose **Input**\.

   1. On the right, in the **Audio selectors** section, under **Audio selector 1**, choose **External file**\.

   1. For **External file**, provide the path and file name to the \.wav file for your first channel\. For **Audio selector 1**, this channel must be L\. 
**Important**  
You must set up the channels in the following order: L, R, C, LFE, Ls, Rs, Lrs, Rrs, Lw, Rw, Ltf, Rtf, Ltm, Rtm, Ltr, Rtr\.   
That is, if your input audio is in separate \.wav files, **Audio selector 1** must point to the L channel, **Audio selector 2** must point to the R channel, and so on\.

   1. At the top of the **Audio selectors** section, choose **Add audio selector** to create **Audio selector 2**\.

   1. Under **Audio selector 2**, choose **External file**\.

   1. Specify the path and file name to the \.wav file for your second channel\. For **Audio selector 2**, this channel must be R\.

   1. Repeat the steps to create an audio selector for the rest of your 16 channels\. Choose the following channels for each selector:
      + **Audio selector 3**: C
      + **Audio selector 4**: LFE
      + **Audio selector 5**: Ls
      + **Audio selector 6**: Rs
      + **Audio selector 7**: Lrs
      + **Audio selector 8**: Rrs
      + **Audio selector 9**: Lw
      + **Audio selector 10**: Rw
      + **Audio selector 11**: Ltf
      + **Audio selector 12**: Rtf
      + **Audio selector 13**: Ltm
      + **Audio selector 14**: Rtm
      + **Audio selector 15**: Ltr
      + **Audio selector 16**: Rtr

1. Create an input **Audio selector group** as follows:

   1. In the **Audio selector groups** section, choose **Add audio selector group**\.

   1. For **Group name**, enter a descriptive name, such as **Dolby Atmos Audio Group**\.

   1. For **Select audio selectors**, choose each audio selector that you created earlier in this procedure\. Choose them in order, starting with **Audio selector 1**\.

1. Set up your output groups, outputs, and video output selectors as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring complex jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\. Choose supported containers as listed in [Feature Restrictions for Dolby Atmos Encoding](#feature-restrictions-for-dolby-atmos-encoding)\.

1. Create audio output selectors as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring complex jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\.

   Set them up as follows:

   1. In the **Job** pane on the left, choose an output that includes audio\.

   1. In the **Encoding settings** section, choose **Audio 1**\.

   1. For **Audio codec**, choose **Dolby Digital Plus JOC \(Atmos\)**\.

      For **Audio source**, choose the audio selector group that you created earlier in this procedure, such as **Dolby Atmos Audio Group**\.

   1. For the audio encoding settings, choose values that are suitable for your workflow\. For more information, see the Dolby documentation for the Dolby Digital Plus Atmos encoding library\.
**Note**  
AWS Elemental MediaConvert automatically performs audio normalization on Dolby Digital Plus Atmos outputs\. Therefore, there is no **Dialnorm** setting under audio encoding settings\.

**To set up a Dolby Atmos job, with audio input as a single file with 16 tracks**<a name="proc-atmos-single-input-file"></a>

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create job**\.

1. Set up your input video as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. Set up your input audio selectors as follows:

   1. On the **Create job** page, in the **Job** pane on the left, choose **Input**\.

   1. On the right, in the **Audio selectors** section, under **Audio selector 1**, choose **External file**\.

   1. For **External file**, provide the path and file name to the \.wav file\. 

   1. For **Selector type**, choose **Track**\.

   1. For **Tracks**, list your 16 PCM mono tracks in a comma\-separated list\. Specify them in the following order: L, R, C, LFE, Ls, Rs, Lrs, Rrs, Lw, Rw, Ltf, Rtf, Ltm, Rtm, Ltr, Rtr\.
      + If the tracks of your input audio file are already in that order, then list them that way: **1, 2, 3, … 16**\. 
      + If the tracks of your input audio file are in a different order, list them according to the specified order\. For example, if your L channel is in track 3, then list **3** first\.

1. Set up your output groups, outputs, and video output selectors as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring complex jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\. Choose supported containers as listed in [Feature Restrictions for Dolby Atmos Encoding](#feature-restrictions-for-dolby-atmos-encoding)\.

1. Create audio output selectors as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring complex jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\.

   Set them up as follows:

   1. In the **Job** pane on the left, choose an output that includes audio\.

   1. In the **Encoding settings** section, choose **Audio 1**\.

   1. For **Audio codec**, choose **Dolby Digital Plus JOC \(Atmos\)**\.

      For **Audio source**, keep the default **Audio selector 1**\.

   1. For the audio encoding settings, choose values that are suitable for your workflow\. For more information, see the Dolby documentation for the Dolby Digital Plus Atmos encoding library\.
**Note**  
AWS Elemental MediaConvert automatically performs audio normalization on Dolby Digital Plus Atmos outputs\. Therefore, there is no **Dialnorm** setting under audio encoding settings\.