# How Output Groups Affect Outputs in AWS Elemental MediaConvert<a name="outputs-file-ABR"></a>

An AWS Elemental MediaConvert output functions differently depending on which type of output group it is a part of\. In a file output group, each output is a standalone file that contains all the video, audio, and captions together\. In an HLS, DASH, or Smooth output group, each output is one rendition in the ABR stack\. 

A single job can generate zero to many  standalone files and zero to many HLS, DASH, and Smooth ABR stacks\. To create more than one standalone file, add a single file output group to your job and add multiple outputs to that output group\. To create more than one ABR stack, add multiple HLS, DASH, or Smooth output groups to your job\.

The following example shows how an AWS Elemental MediaConvert job generates two standalone \.mp4 files, two HLS ABR stacks, and a DASH ABR stack\.  

![\[Many files can be created from one job.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/jobSetupToOutput.png)

For information about setting up output groups and outputs within your job, see [Setting Up a Job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

After you create your outputs within the appropriate output groups, use selectors to specify the video, audio, and captions that you want AWS Elemental MediaConvert to include in each output\. For more information, see [Including Video, Audio, and Captions in Outputs in AWS Elemental MediaConvert](video-audio-captions-selectors.md)\. 