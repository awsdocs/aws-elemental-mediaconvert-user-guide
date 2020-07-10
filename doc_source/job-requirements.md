# Job limitations for accelerated transcoding in AWS Elemental MediaConvert<a name="job-requirements"></a>

Before you enable accelerated transcoding, make sure that your job conforms to the following requirements and limitations\.

**Video inputs supported with accelerated transcoding**  
The following table shows the video input codecs and containers that MediaConvert supports with accelerated transcoding\.


| Container | Video Codecs Supported with Container | 
| --- | --- | 
| IMF | JPEG 2000 \(J2K\) | 
| MPEG Transport Streams | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2, VC\-1 | 
| MPEG\-4 | AVC Intra 50/100, AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2 | 
| MXF | Apple ProRes, AVC Intra 50/100, AVC \(H\.264\), JPEG 2000 \(J2K\), MPEG\-2, SonyXDCam, SonyXDCam \(as an MPEG\-2 variant only\) | 
| QuickTime | Apple ProRes, AVC Intra 50/100, AVC \(H\.264\), JPEG 2000 \(J2K\), MPEG\-2 | 

**Video outputs supported with accelerated transcoding**  
The following table shows the video output codecs and containers that MediaConvert supports with accelerated transcoding\.


| Container | Codecs Supported with Container | 
| --- | --- | 
| CMAF | AV1, AVC \(H\.264\), HEVC \(H\.265\) | 
| DASH | AV1, AVC \(H\.264\), HEVC \(H\.265\) | 
| HLS | AVC \(H\.264\), HEVC \(H\.265\) | 
| MPEG\-2 TS | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2 | 
| MPEG\-4 \(\.mp4\) | AV1, AVC \(H\.264\), HEVC \(H\.265\) | 
| MPEG\-4 Flash \(\.f4v\) | AVC \(H\.264\) | 
| MXF \(\.mxf\) | MPEG\-2 | 
| QuickTime | AVC \(H\.264\), MPEG\-2 | 
| Smooth \(ISMV\) | AVC \(H\.264\) | 
| Raw \(no container\) | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2 | 

**Note**  
For MPEG\-2 TS outputs, to use accelerated transcoding, you must change the default value of **CBR** for **Transport stream settings** > **Rate mode** to **VBR**\.

**Output restrictions**
+ Use only supported combinations of container and codec\. The preceding table shows the supported video output codecs and containers\.
+ Use only supported output captions formats\. For accelerated transcoding, MediaConvert doesn’t support the following output captions formats:
  + Not supported: Burn\-in
  + Not supported: SCTE\-20

  For a list of supported captions formats, see [Captions support tables by output container type](captions-support-tables-by-container-type.md)\.

**Transcoding features not supported with accelerated transcoding**
+ Avail blanking
+ Motion image inserter \(Motion graphic overlay\)
+ Interpolated frame rate conversion
+ VBI passthrough
+ Timecode passthrough
+ SEI timecode
+ Timecode anchor
+ Telecine output
+ Inverse telecine output
+ Open GOP outputs
+ Embedded timecode source
**Note**  
With accelerated transcoding, you can set the input setting **Timecode source** to **Embedded**, but not the job\-wide setting **Source** under **Timecode configuration**\.
+ Values for Min\-I interval other than the default of 0
+ ESAM
+ SCTE\-35 passthrough