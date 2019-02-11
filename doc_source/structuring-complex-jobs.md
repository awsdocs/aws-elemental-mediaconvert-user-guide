# Structuring Complex Jobs in AWS Elemental MediaConvert<a name="structuring-complex-jobs"></a>

A single MediaConvert job can create outputs in the form of a standalone file \(for example, an \.mp4 file\), a set of files for adaptive bitrate \(ABR\) streaming \(for example, an Apple HLS package\), or combinations of both\. 

You specify the number and types of files that your job generates by creating output groups and outputs within them\. 

The topics in this section explain the relationship between output groups, outputs, and the actual output files that MediaConvert produces\. 

**Topics**
+ [How Output Groups Affect Outputs in MediaConvert](outputs-file-ABR.md)
+ [Choosing Your ABR Streaming Output Groups](choosing-your-streaming-output-groups.md)
+ [HLS Player Version Support](hls-player-version-support.md)