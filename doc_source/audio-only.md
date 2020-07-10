# Using AWS Elemental MediaConvert to create outputs with only audio<a name="audio-only"></a>

You can use AWS Elemental MediaConvert to create outputs that contain only audio, without video\. With audio\-only outputs, MediaConvert supports a more limited number of codec and container combinations for input and output files\.

**Note**  
The restrictions and procedures in this chapter apply to outputs that don't have video in the container\. This includes the following:  
Outputs in **File** output groups that don't have video included
Streaming **HLS** output groups that contain only audio outputs
When you set up streaming output packages that contain audio, video, and captions, you create separate outputs for each element inside the output package\. These are not audio\-only outputs as described in this chapter\. For more information about setting up streaming outputs, see [Creating outputs in ABR streaming output groups](create-outputs-in-abr-streaming-output-groups.md)\.

**Topics**
+ [Setting up audio\-only outputs](setting-up-audio-only.md)
+ [Supported codecs and containers for audio\-only outputs](supported-codecs-containers-audio-only.md)
+ [Feature limitations](feature-limitations-for-audio-only.md)