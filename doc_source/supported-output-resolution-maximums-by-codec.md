# Supported output resolution maximums by codec<a name="supported-output-resolution-maximums-by-codec"></a>

The following table shows the maximum output resolution AWS Elemental MediaConvert supports for each output codec\.


|  Codec  |  Maximum resolution \(pixels\)  | 
| --- | --- | 
| AV1 | 4096x2160 | 
| AVC\-Intra | 1920x1080 or 1080x1920 | 
|  AVC \(H\.264\)  |  4096x2160 or 2160x4096  | 
|  HEVC \(H\.265\)  |  8192x4320 or 4320x8192  | 
|  MPEG\-2  |  1920x1152  | 
|  Apple ProRes  |  4096x4096  | 
| VC\-3 | 1920x1080 or 1080x1920 | 
| VP8, VP9 |  4096x2160 or 2160x4096  | 
| XAVC |  4096x2160  | 

## 8k output resolution job restrictions<a name="8k-output-resolution-job-restrictions"></a>

When your MediaConvert job has outputs with 8k \(8192x4320\) resolutions, your job is restricted in these ways:
+ You can't create Dolby Vision outputs\.
+ You must send your job to an on\-demand queue\. Reserved queues can't run 8k jobs\.

## Preserving 4:4:4 Chroma sampling<a name="apple-prores-4444-preserve"></a>

When your MediaConvert job has Apple ProRes outputs that need to have 4:4:4 chroma subsampling preserved, your job is restricted in these ways:
+ You can only use the NexGuard File Maker preprocessor\.
+  You must use the Duplicate Drop as the frame rate conversion algorithm when using frame rate convesion\. 
+ You cannot mix RGB and non RGB inputs\.
+ You cannot mix 4:4:4 inputs with non 4:4:4 inputs\.