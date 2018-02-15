# Setting Up a Job in AWS Elemental MediaConvert<a name="setting-up-a-job"></a>

A job does the work of transcoding a media file\. When you create a job, you specify the information that AWS Elemental MediaConvert needs to perform the transcode: which file to transcode, what to name the transcoded files, which encoding settings to use, which advanced features to apply, and so on\. 

You also create output groups and outputs, and then specify the output settings\. For information about how different ways of setting up outputs and output groups affects the assets produced by your job, see [[ERROR] BAD/MISSING LINK TEXT](structuring-complex-jobs.md)\.

## Specify Input Settings<a name="specify-input-settings"></a>

When you set up a job through the AWS Elemental MediaConvert console, you begin with input settings\. 

**To specify the location of your input:**

1. On the **Create job** page, under **Input 1**, provide the URI to your input file stored in Amazon S3 \.

   If you want to transcode only a portion of this input file, choose **Add input clip** and specify the portion\.

1. Specify values for any of the following video selector fields that are applicable to your job\. 

   If you leave these settings in their default state, you will create a valid job\. For more information on individual settings, choose the **Info** link next to the setting\.

1. Create audio selectors for any audio assets from the input used in an input\. For more information on setting up audio for your job, see [Setting Up Audio in AWS Elemental MediaConvert Jobs](setting-up-audio.md)

1. Create captions selectors for any captions assets from the input used in an output\. For more information on setting up captions for your job, see [Setting Up Captions in AWS Elemental MediaConvert Jobs](including-captions.md)

1. To include another input in this job, in the **Job** navigation pane on the left, choose **Add input**\.

   For jobs that have multiple input files, the transcoding service creates outputs by concatenating the input files or clips\.

### <a name="input-settings-captions"></a>

## Create Output Groups<a name="specify-output-groups"></a>

After specifying your input settings, create output groups\. Each output that AWS Elemental MediaConvert creates must reside in an output group\. For adaptive bitrate \(ABR\) output groups, every output in an output group is packaged in the same ABR stack\. For file group output groups, each output is a standalone file\. For more information on how your choices of output group and outputs within the group affect the assets created by your job, see [[ERROR] BAD/MISSING LINK TEXT](structuring-complex-jobs.md)\.

**To create an output group:**

1. From the **Job **navigation pane on the left, choose the **Add output group**\.

1. Choose an output group type, and then choose **Select**\. 

1. Optionally, provide a name under **Custom group name**\. Any name you provide here will appear in the **Job** navigation pane on the left\. 

1. Under **Destination**, specify the URI for the Amazon S3 location where the trancoding service will store your output files\.
**Note**  
You can optionally append a basename to your destination URI\. The transcoding service will use this basename in conjunction with any name modifier you provide in the individual output settings to create the filename of your final asset\.  
If you do not provide a basename with your URI, the transcoding service will generate a basename from the Input 1 filename, minus the extension\.

1. Specify the values for the encoding settings that apply to the entire output group\. These settings vary depending on which type of output group that you select\.

You can create multiple output groups and multiple types of output groups\. After you create your output groups, set up the individual outputs within each group\. 

## Create Outputs and Specify Output Settings<a name="specify-output-settings"></a>

After creating output groups, set up your outputs within each group\. For more information on how your choices of output group and outputs within the group affect the assets created by your job, see [[ERROR] BAD/MISSING LINK TEXT](structuring-complex-jobs.md)\. You can set up an output either by selecting a preset, which is a pre\-defined set of values for the output settings, or by specifying the settings individually\.

**To set up the outputs in an output group:**

1. Specify a value for **Name modifier** and **Extension** in **Output 1**\. When you create an output group, AWS Elemental MediaConvert automatically populates the output group with output 1, so you do not need to explicitly create it\.

   The transcoding service will append the name modifier and extension to the basename to generate the filename it gives this output\.

1. If one of the predefined groups of settings listed under **Preset** is suitable for your workflow, choose it from the list\. If you use a preset, skip the rest of the steps in this procedure\.

1. Specify values for the general settings under **Output settings**\. Depending on the output group type, these settings may include transport stream settings or other container settings\. For more information on individual settings, choose the **Info** link next to the setting\.

1. Specify values for the video encoding under **Encoding settings**\. The video settings are selected by default, so you don't need to explictly choose this group of settings\.

   For more information on individual settings, choose the **Info** link next to the setting\.

1. Choose **Audio 1** to bring up the group of encoding settings for the first audio asset included in this output\. For more information on bringing audio from the input to each output, see [Setting Up Audio in AWS Elemental MediaConvert Jobs](setting-up-audio.md)

1. To include captions in the output, choose **Add captions** to bring up a group of captions settings\. For more information on setting up captions, see [Setting Up Captions in AWS Elemental MediaConvert Jobs](including-captions.md)

1. If you want more outputs in this output group, choose the **Add output** link under your output group name\. 

## Specify Global Job Settings<a name="specify-global-job-settings"></a>

Global job settings apply to every output created by the job\. 

1. In the **Job** navigation pane on the left, under **Job settings**, choose **Settings**\.

1. Under **IAM role**, choose an IAM role that has permissions to access the Amazon S3 buckets that hold your input and output files and has a trusted relationship with AWS Elemental MediaConvert\. For information on creating this role, see [Step 3: Set Up IAM Permissions](iam-role.md)\.

1. Optionally, specify values for the other job settings and enable global processors\. For more information on individual settings, choose the **Info** link next to the setting\.