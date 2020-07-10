# Captions support tables by output container type<a name="captions-support-tables-by-container-type"></a>

**Topics**
+ [CMAF output container](#cmaf-output-container)
+ [DASH output container](#dash-output-container)
+ [HLS output container](#hls-output-container)
+ [MS smooth \(MSS\) output container](#mss-output-container)
+ [MP4 output container](#mp4-output-container)
+ [MPEG2\-TS File output container](#mpeg2-ts-file-output-container)
+ [MXF output container](#mxf-output-container)
+ [QuickTime output container](#quicktime-output-container)
+ [No output container](#no-output-container)

## CMAF output container<a name="cmaf-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  MP4 Container  |  Embedded  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|   |  SCTE\-20  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  MXF Container  |  Embedded  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|   |  Ancillary  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  QuickTime Container  |  Embedded  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|   |  Ancillary  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  Raw Container  |  IMSC1 text profile  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|   |  SRT  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|   |  TTML  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|   |  STL  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|   |  SCC  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|   |  SMI  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  MPEG2\-TS Container  |  Embedded  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|   |  SCTE\-20  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|   |  Teletext  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## DASH output container<a name="dash-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMF Container  Specify the CPL to define your input\.   |  IMSC1 text profile  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  MP4 Container  |  Embedded  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\) WebVTT  | 
|   |  SCTE\-20  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  MPEG2\-TS Container  | DVB\-Sub |  Burn in  | 
|   |  Embedded  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\) WebVTT  | 
|   |  SCTE\-20  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\) WebVTT  | 
|   |  Teletext  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  MXF Container  |  Embedded  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|   |  SCTE\-20  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|   |  Ancillary  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|   |  Teletext  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  QuickTime Container  |  Embedded  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|   |  SCTE\-20  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|   |  Ancillary  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  Raw Container  |  IMSC1 text profile  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  |  SRT  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|   |  TTML  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|   |  STL  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|   |  SCC  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|   |  SMI  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## HLS output container<a name="hls-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 

**Note**  
For HLS outputs, if your input caption format is Teletext or DVB\-Sub, you can include output captions in those formats as well\. Standard Apple players will not recognize those captions, but custom players may\. 

**Note**  
AWS Elemental MediaConvert has the following limitations with Teletext in outputs:  
The service doesn't support captions formatting and positioning
You can use only [Teletext level 1\.5](https://en.wikipedia.org/wiki/World_System_Teletext) languages


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMF Container  Specify the CPL to define your input\.   |  IMSC1 text profile  |  WebVTT  | 
|  MP4 Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|  MXF Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   |  Teletext  |  Burn in  | 
|  QuickTime Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|  Raw Container  |  IMSC1 text profile  |  Burn in WebVTT  | 
|  |  SRT  |  Burn in WebVTT  | 
|   |  TTML  |  Burn in WebVTT  | 
|   |  STL  |  Burn in WebVTT  | 
|   |  SCC  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   |  SMI  |  Burn in WebVTT  | 
|  MPEG2\-TS Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   |  Teletext  |  Burn in WebVTT  | 
|   | DVB\-Sub |  Burn in  | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## MS smooth \(MSS\) output container<a name="mss-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  MP4 Container  |  Embedded  |  Burn in TTML  | 
|   |  SCTE\-20  |  Burn in TTML  | 
|  MXF Container  |  Embedded  |  Burn in TTML  | 
|   |  SCTE\-20  |  Burn in TTML  | 
|   |  Ancillary  |  Burn in TTML  | 
|   |  Teletext  |  Burn in TTML  | 
|  QuickTime Container  |  Embedded  |  Burn in TTML  | 
|   |  SCTE\-20  |  Burn in TTML  | 
|   |  Ancillary  |  Burn in TTML  | 
|  Raw Container  |  IMSC1 text profile  |  Burn in TTML  | 
|  |  SRT  |  Burn in TTML  | 
|   |  SMI  |  Burn in TTML  | 
|   |  TTML  |  Burn in TTML  | 
|   |  STL  |  Burn in TTML  | 
|   |  SCC  |  Burn in TTML  | 
|   |  SMI  |  Burn in TTML  | 
|  MPEG2\-TS Container  |  Embedded  |  Burn in TTML  | 
|   |  SCTE\-20  |  Burn in TTML  | 
|   |  Teletext  |  Burn in TTML  | 
|   | DVB\-Sub |  Burn in  | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## MP4 output container<a name="mp4-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  MP4 Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  MXF Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Teletext  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  QuickTime Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  Raw Container  |  IMSC1 text profile  |  Burn in  | 
|  |  SRT  |  Burn in  | 
|   |  TTML  |  Burn in  | 
|   |  STL  |  Burn in  | 
|   |  SCC  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SMI  |  Burn in  | 
|  MPEG2\-TS Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Teletext  |  Burn in  | 
|   | DVB\-Sub |  Burn in  | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## MPEG2\-TS File output container<a name="mpeg2-ts-file-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 

**Note**  
AWS Elemental MediaConvert has the following limitations with Teletext in outputs:  
The service doesn't support captions formatting and positioning
You can use only [Teletext level 1\.5](https://en.wikipedia.org/wiki/World_System_Teletext) languages


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMF Container  Specify the CPL to define your input\.   |  IMSC1 text profile  |  Burn in DVB\-Sub Teletext  | 
|  MP4 Container  |  Embedded  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  MXF Container  |  Embedded  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Ancillary  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Teletext  |  Burn in DVB\-Sub Teletext  | 
|  QuickTime Container  |  Embedded  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Ancillary  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  Raw Container  |  IMSC1 text profile  |  Burn in Teletext DVB\-Sub  | 
|  |  SRT  |  Burn in Teletext  | 
|   |  SMI  |  Burn in DVB\-Sub  | 
|   |  TTML  |  Burn in Teletext DVB\-Sub  | 
|   |  STL  |  Burn in Teletext DVB\-Sub  | 
|   |  SCC  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SMI  |  Burn in DVB\-Sub  | 
|  MPEG2\-TS Container  |  Embedded  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Teletext  |  Burn in DVB\-Sub Teletext  | 
|   | DVB\-Sub |  Burn in DVB\-Sub  | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## MXF output container<a name="mxf-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMF Container  Specify the CPL to define your input\.   |  IMSC1 text profile  |  Burn in  | 
|  MP4 Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  MPEG2\-TS Container  | DVB\-Sub |  Burn in  | 
|  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  |  Teletext  |  Burn in  | 
|  MXF Container  |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  QuickTime Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  Raw Container  |  IMSC1 text profile  |  Burn in  | 
|  |  SRT  |  Burn in  | 
|   |  TTML  |  Burn in  | 
|   |  STL  |  Burn in  | 
|   |  SCC  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SMI  |  Burn in  | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## QuickTime output container<a name="quicktime-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMF Container  Specify the CPL to define your input\.   |  IMSC1 text profile  |  Burn in  | 
|  MP4 Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  MXF Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Teletext  |  Burn in  | 
|  QuickTime Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|  Raw Container  |  IMSC1 text profile  |  Burn in  | 
|  |  SRT  |  Burn in  | 
|   |  TTML  |  Burn in  | 
|   |  STL  |  Burn in  | 
|   |  SCC  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SMI  |  Burn in  | 
|  MPEG2\-TS Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   |  Teletext  |  Burn in  | 
|   |  DVB\-Sub  |  Burn in  | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## No output container<a name="no-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 

**Note**  
You can create sidecar captions outputs only as part of a job that also generates a video output\.


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  MP4 Container  |  Embedded  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|   |  SCTE\-20  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|  MXF Container  |  Embedded  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|   |  SCTE\-20  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|   |  Ancillary  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|   |  Teletext  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|  QuickTime Container  |  Embedded  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|   |  SCTE\-20  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|   |  Ancillary  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|  Raw Container  |  IMSC1 text profile  |  IMSC \(as sidecar \.xml\) IMSC SRT SMI TTML WebVTT  | 
|   |  SRT  |  IMSC \(as sidecar \.xml\) IMSC SRT SMI TTML WebVTT  | 
|   |  TTML  |  IMSC \(as sidecar \.xml\) SRT SMI TTML WebVTT  | 
|   |  STL  |  IMSC \(as sidecar \.xml\) SRT SMI TTML WebVTT  | 
|   |  SCC  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|   |  SMI  |  IMSC \(as sidecar \.xml\) SRT SMI TTML WebVTT  | 
|  MPEG2\-TS Container  |  Embedded  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|   |  SCTE\-20  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|   |  Teletext  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data