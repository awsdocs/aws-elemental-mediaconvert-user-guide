# Supported output resolution maximums by codec<a name="supported-output-resolution-maximums-by-codec"></a>

The following table shows the maximum output resolution AWS Elemental MediaConvert supports for each output codec\.


|  Codec  |  Maximum resolution \(pixels\)  | 
| --- | --- | 
| AV1 | 1920x1080 or 1080x1920 | 
| AVC\-Intra | 1920x1080 or 1080x1920 | 
|  AVC \(H\.264\)  |  4096x2160 or 2160x4096  | 
|  HEVC \(H\.265\)  |  8192x4320 or 4320x8192  | 
|  MPEG\-2  |  1920x1152  | 
|  Apple ProRes  |  4096x4096  | 
| VC\-3 | 1920x1080 or 1080x1920 | 
| VP8, VP9 |  4096x2160 or 2160x4096  | 

## 8k output resolution job restrictions<a name="8k-output-resolution-job-restrictions"></a>

When your MediaConvert job has outputs with 8k \(8192x4320\) resolutions, your job is restricted in these ways:
+ You can't create Dolby Vision outputs\.
+ You must send your job to an on\-demand queue\. Reserved queues can't run 8k jobs\.