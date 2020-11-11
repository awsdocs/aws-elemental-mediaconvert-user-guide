# Creating outputs with AWS Elemental MediaConvert<a name="creating-streaming-and-file-outputs"></a>

A single MediaConvert job can create outputs in the form of a standalone file \(for example, an \.mp4 file\), a set of files for adaptive bitrate \(ABR\) streaming \(for example, an Apple HLS package\), or combinations of both\. When you create output groups and the outputs within them, you specify the number and types of files that your job generates\.

When your MediaConvert job is complete, you can use Amazon CloudFront, or another content distribution network \(CDN\), to deliver your streaming package\. The CDN gets your video to the people who want to view it\. For more information, see [Delivering video on demand \(VOD\) with CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/on-demand-video.html)\.

The topics in this section explain the relationship between MediaConvert output groups, MediaConvert outputs, and the actual output files that MediaConvert delivers to you\. 

**Topics**
+ [Using AWS Elemental MediaConvert output groups to specify a streaming package type or standalone file](outputs-file-ABR.md)
+ [Choosing your ABR streaming output groups](choosing-your-streaming-output-groups.md)
+ [HLS player version support](hls-player-version-support.md)