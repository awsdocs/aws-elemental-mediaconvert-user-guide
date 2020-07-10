# How output groups affect outputs in MediaConvert<a name="outputs-file-ABR"></a>

An MediaConvert output functions differently depending on which type of output group it is a part of\. In a **File** output group, each output is a standalone file that contains all the video, audio, and captions together\. 

In an adaptive bitrate \(ABR\) streaming output group—**CMAF**, **AppleHLS**, **DASH ISO**, or **Microsoft Smooth Streaming**—each output is one element of the media\. For example, you might have one resolution of video, one audio language track, and one captions language\. That is, each output is one rendition in the adaptive bitrate \(ABR\) stack\. 

The following illustration shows files created from a streaming output group\. Each orange box corresponds to an output within the output group\. In this example, there are three resolutions of video, audio in two languages, and captions in two languages\. The package contains segmented audio, video, and captions files and manifest files that tell the player which files to download and when to play them\.

![\[Each rendition in an ABR stack has its own output in the output group.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/ABRsegSeparately.png)

A single job can generate zero to many  standalone files and zero to many streaming packages\. To create more than one standalone file, add a single file output group to your job and add multiple outputs to that output group\. To create more than one streaming package, add multiple **CMAF**, **AppleHLS**, **DASH ISO**, or **Microsoft Smooth Streaming** output groups to your job\.

The following illustration shows an MediaConvert job that generates two standalone \.mp4 files, two Apple HLS packages, and a CMAF package\.  

![\[A single file output group with two outputs results in two standalone files. A single Apple HLS output group with seven outputs results in a single viewable package with seven renditions.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/jobSetupToOutput.png)

For information about setting up output groups and outputs within your job, see [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.