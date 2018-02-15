# Structuring Complex Jobs in AWS Elemental MediaConvert<a name="structuring-complex-jobs"></a>

A single AWS Elemental MediaConvert job can create outputs in the form of a standalone file \(for example, an \.mp4 file\), a set of files for ABR \(for example, an HLS package\), or combinations of both\. 

You specify the number and types of files that your job generates by creating outputs within output groups\. 

The topics in this section explain the relationship between outputs, output groups, and the actual output files that are produced by AWS Elemental MediaConvert\. 


+ [How Output Groups Affect Outputs in AWS Elemental MediaConvert](outputs-file-ABR.md)
+ [Including Video, Audio, and Captions in Outputs in AWS Elemental MediaConvert](video-audio-captions-selectors.md)
+ [HLS Player Version Support](hls-player-version-support.md)