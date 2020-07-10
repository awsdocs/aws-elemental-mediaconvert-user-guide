# Supported output resolution maximums by codec<a name="supported-output-resolution-maximums-by-codec"></a>

The following table shows the maximum output resolution AWS Elemental MediaConvert supports for each output codec\.


|  Codec  |  Maximum resolution \(pixels\)  | 
| --- | --- | 
|  HEVC \(H\.265\)  |  8192x4320 or 4320x8192  | 
|  AVC \(H\.264\)  |  4096x2160 or 2160x4096  | 
| VP8, VP9 |  4096x2160 or 2160x4096  | 
|  Apple ProRes  |  4096x4096  | 
|  MPEG\-2  |  1920x1152  | 

## 8k output resolution job restrictions<a name="8k-output-resolution-job-restrictions"></a>

When your MediaConvert job has outputs with 8k \(8192x4320\) resolutions, your job is restricted in these ways:
+ You can't create Dolby Vision outputs\.
+ You must send your job to an on\-demand queue\. Reserved queues can't run 8k jobs\.