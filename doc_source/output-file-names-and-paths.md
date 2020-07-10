# Output file names and paths<a name="output-file-names-and-paths"></a>

The CloudWatch Events job `COMPLETE` notification includes the `JobResult` response in JSON\. This information includes the file names and paths for the outputs of the job—including manifests as well as the media assets\.

The files that AWS Elemental MediaConvert creates depends on the output groups that you set up in the job\. For example, DASH ISO packages contain an \.mpd manifest and \.mp4 media fragment files\.

You can find output file name and path information in the `JobResult` response information, in the following properties:

playlistFilePaths  
A list of the Amazon S3 file paths to the top\-level manifests\.

outputFilePaths  
The file path to either the media or the manifest, depending on the output group type\.

type  
The type of output group, which determines what files are listed in the `playlistFilePaths` and `outputFilePaths`\.

The following table summarizes the values for these properties, depending on the output group type\.


| Type | playlistFilePaths | outputFilePaths | 
| --- | --- | --- | 
| FILE\_GROUP \(standard output\) | not returned |  File name and path of the media file Example: `s3://bucket/file/file.mp4`  | 
| FILE\_GROUP \(with additional frame capture output\) | not returned |  File name and path of the final captured image Example: `s3://bucket/frameoutput/file.0000036.jpg`  | 
| HLS\_GROUP |  File name and path of the top\-level manifest Example: `s3://bucket/hls/main.m3u8`  |  File name and path of the manifests for the individual outputs Examples: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/output-file-names-and-paths.html)  | 
| DASH\_ISO\_GROUP |  File name and path of the manifest Example: `s3://bucket/dash/1.mpd`  | not returned | 
| CMAF\_GROUP |  File name and path for each of the top\-level manifests Examples: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/output-file-names-and-paths.html)  | not returned | 
| MS\_SMOOTH\_GROUP |  File name and path of the server\-side manifest Example: `s3://bucket/smooth/1.ism`  |  File name and path of the video manifests for each of the individual outputs Examples: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/output-file-names-and-paths.html)  | 

For sample `JobResult` responses in JSON for each output group type, see the following topics:

**Topics**
+ [File group](file-group.md)
+ [File group with a frame capture output](file-group-with-frame-capture-output.md)
+ [Apple HLS group](apple-hls-group.md)
+ [DASH ISO group](dash-iso-group.md)
+ [CMAF group](cmaf-group.md)
+ [Microsoft Smooth Streaming group](microsoft-smooth-streaming-group.md)