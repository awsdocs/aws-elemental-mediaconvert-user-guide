# Job Limitations for Accelerated Transcoding in AWS Elemental MediaConvert<a name="job-requirements"></a>

Before you enable accelerated transcoding, make sure that your job conforms to the following requirements and limitations\.

**Video Input Requirements**  
The following table shows the supported video input codecs and containers\.


| Container | Video Codecs Supported with Container | 
| --- | --- | 
| IMF | JPEG 2000 \(J2K\) | 
| MPEG Transport Streams | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2, VC\-1 | 
| MPEG\-4 | AVC Intra 50/100, AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2 | 
| MXF | Apple ProRes, AVC Intra 50/100, AVC \(H\.264\), JPEG 2000 \(J2K\), MPEG\-2, SonyXDCam, SonyXDCam \(as an MPEG\-2 variant only\) | 
| QuickTime | Apple ProRes, AVC Intra 50/100, AVC \(H\.264\), JPEG 2000 \(J2K\), MPEG\-2 | 

**Output Restrictions**
+ You can't set up an output for frame capture\. That is, you can't choose **Frame Capture to JPEG** for **Video codec** in any of your outputs\.
+ Use only supported combinations of container and codec\. The following table shows the supported video output codecs and containers\.    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/job-requirements.html)
**Note**  
For MPEG\-2 TS outputs, to use accelerated transcoding, you must change the default value of **CBR** for **Transport stream settings** > **Rate mode** to **VBR**\.
+ Use only supported output captions formats\. For accelerated transcoding, MediaConvert doesn’t support the following output captions formats:
  + Not supported: Burn\-in
  + Not supported: SCTE\-20

  For a list of supported captions formats, see [Captions Support Tables by Output Container Type](captions-support-tables-by-container-type.md)\.

**Transcoding Features Not Supported with Accelerated Transcoding**
+ Slow PAL
+ Avail blanking
+ Motion image inserter \(Motion graphic overlay\)
+ Interpolated frame rate conversion
+ Frame capture to JPEG
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