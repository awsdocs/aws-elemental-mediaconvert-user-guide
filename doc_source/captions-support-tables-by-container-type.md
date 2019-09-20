# Captions Support Tables by Output Container Type<a name="captions-support-tables-by-container-type"></a>

**Topics**
+ [CMAF Output Container](#cmaf-output-container)
+ [DASH Output Container](#dash-output-container)
+ [HLS Output Container](#hls-output-container)
+ [MS Smooth \(MSS\) Output Container](#mss-output-container)
+ [MP4 Output Container](#mp4-output-container)
+ [MPEG2\-TS File Output Container](#mpeg2-ts-file-output-container)
+ [MXF Output Container](#mxf-output-container)
+ [QuickTime Output Container](#quicktime-output-container)
+ [No Output Container](#no-output-container)

## CMAF Output Container<a name="cmaf-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


| Input Captions Container | Input Captions Format | Supported Output Captions Formats | 
| --- | --- | --- | 
| MP4 Container | Embedded | WebVTT | 
|   | SCTE\-20 | WebVTT | 
| MXF Container | Embedded | WebVTT | 
|   | Ancillary | WebVTT | 
| QuickTime Container | Embedded | WebVTT | 
|   | Ancillary | WebVTT | 
| Raw Container | SRT | WebVTT | 
|   | TTML | WebVTT | 
|   | STL | WebVTT | 
|   | SCC | WebVTT | 
|   | SMI | WebVTT | 
| MPEG2\-TS Container | Embedded | WebVTT | 
|   | SCTE\-20 | WebVTT | 
|   | Teletext | WebVTT | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## DASH Output Container<a name="dash-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


| Input Captions Container | Input Captions Format | Supported Output Captions Formats | 
| --- | --- | --- | 
| IMF Container Specify the CPL to define your input\.  | IMSC1 text profile | Burn in TTML | 
| MP4 Container | Embedded | Burn inTTML | 
|   | SCTE\-20 | Burn inTTML | 
| MPEG2\-TS Container | DVB\-Sub | Burn in | 
|   | Embedded | Burn inTTMLWebVTT | 
|   | SCTE\-20 | Burn inTTMLWebVTT | 
|   | Teletext | Burn inTTML | 
| MXF Container | Embedded | Burn inTTML | 
|   | SCTE\-20 | Burn inTTML | 
|   | Ancillary | Burn inTTML | 
|   | Teletext | Burn inTTML | 
| QuickTime Container | Embedded | Burn inTTML | 
|   | SCTE\-20 | Burn inTTML | 
|   | Ancillary | Burn inTTML | 
| Raw Container | SRT | Burn inTTML | 
|   | TTML | Burn inTTML | 
|   | STL | Burn inTTML | 
|   | SCC | Burn inTTML | 
|   | SMI | Burn inTTML | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## HLS Output Container<a name="hls-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 

**Note**  
For HLS outputs, if your input caption format is Teletext or DVB\-Sub, you can include output captions in those formats as well\. Standard Apple players will not recognize those captions, but custom players may\. 

**Note**  
AWS Elemental MediaConvert has the following limitations with Teletext in outputs:  
The service doesn't support captions formatting and positioning
You can use only [Teletext level 1\.5](https://en.wikipedia.org/wiki/World_System_Teletext) languages


| Input Captions Container | Input Captions Format | Supported Output Captions Formats | 
| --- | --- | --- | 
| IMF Container Specify the CPL to define your input\.  | IMSC1 text profile | WebVTT | 
| MP4 Container | Embedded |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | SCTE\-20 |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
| MXF Container | Embedded |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | SCTE\-20 |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | Ancillary |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | Teletext |  Burn in TTML  | 
| QuickTime Container | Embedded |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | SCTE\-20 |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | Ancillary |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
| Raw Container | SRT |  Burn in WebVTT  | 
|   | TTML |  Burn in WebVTT  | 
|   | STL |  Burn in WebVTT  | 
|   | SCC |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | SMI |  Burn in WebVTT  | 
| MPEG2\-TS Container | Embedded |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | SCTE\-20 |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | Teletext |  Burn in WebVTT  | 
|   | DVB\-Sub | Burn in | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## MS Smooth \(MSS\) Output Container<a name="mss-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


| Input Captions Container | Input Captions Format | Supported Output Captions Formats | 
| --- | --- | --- | 
| IMF Container Specify the CPL to define your input\.  | IMSC1 text profile | Burn inTTML | 
| MP4 Container | Embedded | Burn inTTML | 
|   | SCTE\-20 | Burn inTTML | 
| MXF Container | Embedded | Burn inTTML | 
|   | SCTE\-20 | Burn inTTML | 
|   | Ancillary | Burn inTTML | 
|   | Teletext | Burn inTTML | 
| QuickTime Container | Embedded | Burn inTTML | 
|   | SCTE\-20 | Burn inTTML | 
|   | Ancillary | Burn inTTML | 
| Raw Container | SRT | Burn inTTML | 
|   | SMI | Burn inTTML | 
|   | TTML | Burn inTTML | 
|   | STL | Burn inTTML | 
|   | SCC | Burn inTTML | 
|   | SMI | Burn inTTML | 
| MPEG2\-TS Container | Embedded | Burn inTTML | 
|   | SCTE\-20 | Burn inTTML | 
|   | Teletext | Burn inTTML | 
|   | DVB\-Sub | Burn in | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## MP4 Output Container<a name="mp4-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


| Input Captions Container | Input Captions Format | Supported Output Captions Formats | 
| --- | --- | --- | 
| MP4 Container | Embedded | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| MXF Container | Embedded | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Ancillary | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Teletext | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| QuickTime Container | Embedded | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Ancillary | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| Raw Container | SRT | Burn in | 
|   | TTML | Burn in | 
|   | STL | Burn in | 
|   | SCC | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SMI | Burn in | 
| MPEG2\-TS Container | Embedded | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Teletext | Burn in | 
|   | DVB\-Sub | Burn in | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## MPEG2\-TS File Output Container<a name="mpeg2-ts-file-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 

**Note**  
AWS Elemental MediaConvert has the following limitations with Teletext in outputs:  
The service doesn't support captions formatting and positioning
You can use only [Teletext level 1\.5](https://en.wikipedia.org/wiki/World_System_Teletext) languages


| Input Captions Container | Input Captions Format | Supported Output Captions Formats | 
| --- | --- | --- | 
| IMF Container Specify the CPL to define your input\.  | IMSC1 text profile |  Burn in DVB\-Sub Teletext  | 
| MP4 Container | Embedded |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | SCTE\-20 |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
| MXF Container | Embedded |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | SCTE\-20 |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | Ancillary |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | Teletext |  Burn in DVB\-Sub Teletext  | 
| QuickTime Container | Embedded |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | SCTE\-20 |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | Ancillary |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
| Raw Container | SRT |  Burn in Teletext  | 
|   | SMI |  Burn in DVB\-Sub  | 
|   | TTML |  Burn in Teletext DVB\-Sub  | 
|   | STL |  Burn in Teletext DVB\-Sub  | 
|   | SCC |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | SMI |  Burn in DVB\-Sub  | 
| MPEG2\-TS Container | Embedded | Burn inDVB\-SubEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn inDVB\-SubEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Teletext |  Burn in DVB\-Sub Teletext  | 
|   | DVB\-Sub |  Burn in DVB\-Sub  | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## MXF Output Container<a name="mxf-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


| Input Captions Container | Input Captions Format | Supported Output Captions Formats | 
| --- | --- | --- | 
| IMF Container Specify the CPL to define your input\.  | IMSC1 text profile |  Burn in  | 
| MP4 Container | Embedded |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | SCTE\-20 |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
| MPEG2\-TS Container | DVB\-Sub | Burn inDVB\-Sub | 
|  | Embedded |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | SCTE\-20 |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  | Teletext |  Burn in DVB\-Sub  | 
| MXF Container | Ancillary |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
| QuickTime Container | Embedded |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | SCTE\-20 |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | Ancillary |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
| Raw Container | SRT |  Burn in  | 
|   | TTML |  Burn in  | 
|   | STL |  Burn in  | 
|   | SCC |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | SMI |  Burn in  | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## QuickTime Output Container<a name="quicktime-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


| Input Captions Container | Input Captions Format | Supported Output Captions Formats | 
| --- | --- | --- | 
| IMF Container Specify the CPL to define your input\.  | IMSC1 text profile | Burn in | 
| MP4 Container | Embedded | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| MXF Container | Embedded | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Ancillary | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Teletext | Burn in | 
| QuickTime Container | Embedded | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Ancillary | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| Raw Container | SRT | Burn in | 
|   | TTML | Burn in | 
|   | STL | Burn in | 
|   | SCC | Burn inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   |  SMI  | Burn in | 
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

## No Output Container<a name="no-output-container"></a>

The following table lists supported output captions formats for this output container, sorted by the input captions container and input captions format\. 


|  Input Captions Container  |  Input Captions Format  |  Supported Output Captions Formats  | 
| --- | --- | --- | 
|  MP4 Container  |  Embedded  |  SCC SRT SMI TTML WebVTT  | 
|   |  SCTE\-20  |  SCC SRT SMI TTML WebVTT  | 
|  MXF Container  |  Embedded  |  SCC SRT SMI TTML WebVTT  | 
|   |  SCTE\-20  |  SCC SRT SMI TTML WebVTT  | 
|   |  Ancillary  |  SCC SRT SMI TTML WebVTT  | 
|   |  Teletext  |  SCC SRT SMI TTML WebVTT  | 
|  QuickTime Container  |  Embedded  |  SCC SRT SMI TTML WebVTT  | 
|   |  SCTE\-20  |  SCC SRT SMI TTML WebVTT  | 
|   |  Ancillary  |  SCC SRT SMI TTML WebVTT  | 
|  Raw Container  |  IMSC  |  IMSC SRT SMI TTML WebVTT  | 
|   |  SRT  |  IMSC SRT SMI TTML WebVTT  | 
|   |  TTML  |  SRT SMI TTML WebVTT  | 
|   |  STL  |  SRT SMI TTML WebVTT  | 
|   |  SCC  |  SCC SRT SMI TTML WebVTT  | 
|   |  SMI  |  SRT SMI TTML WebVTT  | 
|  MPEG2\-TS Container  |  Embedded  |  SCC SRT SMI TTML WebVTT  | 
|   |  SCTE\-20  |  SCC SRT SMI TTML WebVTT  | 
|   |  Teletext  |  SCC SRT SMI TTML WebVTT  | 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data