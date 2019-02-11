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

The following table lists supported output caption formats for this output container, sorted by the input caption container and input caption format\. 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the Quicktime Captions Track
+ Captions in the MXF container VANC data


| Input Caption Container | Input Caption Format | Supported Output Caption Formats | 
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

## DASH Output Container<a name="dash-output-container"></a>

The following table lists supported output caption formats for this output container, sorted by the input caption container and input caption format\. 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the Quicktime Captions Track
+ Captions in the MXF container VANC data


| Input Caption Container | Input Caption Format | Supported Output Caption Formats | 
| --- | --- | --- | 
| IMF Container Specify the CPL to define your input\.  | IMSC1 text profile | Burn inTTML | 
| MP4 Container | Embedded | Burn inTTML | 
|   | SCTE\-20 | Burn inTTML | 
| MPEG2\-TS Container | Embedded | WebVTT | 
|   | SCTE\-20 | WebVTT | 
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
| MPEG2\-TS Container | Embedded | Burn inTTML | 
|   | SCTE\-20 | Burn inTTML | 
|   | Teletext | Burn inTTML | 
|   | DVB\-Sub | Burn in | 

## HLS Output Container<a name="hls-output-container"></a>

The following table lists supported output caption formats for this output container, sorted by the input caption container and input caption format\. 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the Quicktime Captions Track
+ Captions in the MXF container VANC data

**Note**  
For HLS outputs, if your input caption format is Teletext or DVB\-Sub, you can include output captions in those formats as well\. Standard Apple players will not recognize those captions, but custom players may\. 

**Note**  
AWS Elemental MediaConvert has the following limitations with Teletext in outputs:  
The service doesn't support captions formatting and positioning
You can use only [Teletext level 1\.5](https://en.wikipedia.org/wiki/World_System_Teletext) languages


| Input Caption Container | Input Caption Format | Supported Output Caption Formats | 
| --- | --- | --- | 
| IMF Container Specify the CPL to define your input\.  | IMSC1 text profile | WebVTT | 
| MP4 Container | Embedded |  Burn\-in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | SCTE\-20 |  Burn\-in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
| MXF Container | Embedded |  Burn\-in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | SCTE\-20 |  Burn\-in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | Ancillary |  Burn\-in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | Teletext |  Burn in TTML  | 
| QuickTime Container | Embedded |  Burn\-in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | SCTE\-20 |  Burn\-in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | Ancillary |  Burn\-in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
| Raw Container | SRT |  Burn\-in WebVTT  | 
|   | TTML |  Burn\-in WebVTT  | 
|   | STL |  Burn\-in WebVTT  | 
|   | SCC |  Burn\-in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | SMI |  Burn\-in WebVTT  | 
| MPEG2\-TS Container | Embedded |  Burn\-in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | SCTE\-20 |  Burn\-in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|   | Teletext |  Burn\-in WebVTT  | 
|   | DVB\-Sub | Burn\-in | 

## MS Smooth \(MSS\) Output Container<a name="mss-output-container"></a>

The following table lists supported output caption formats for this output container, sorted by the input caption container and input caption format\. 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the Quicktime Captions Track
+ Captions in the MXF container VANC data


| Input Caption Container | Input Caption Format | Supported Output Caption Formats | 
| --- | --- | --- | 
| IMF Container Specify the CPL to define your input\.  | IMSC1 text profile | Burn inTTML | 
| MP4 Container | Embedded | Burn\-inTTML | 
|   | SCTE\-20 | Burn\-inTTML | 
| MXF Container | Embedded | Burn\-inTTML | 
|   | SCTE\-20 | Burn\-inTTML | 
|   | Ancillary | Burn\-inTTML | 
|   | Teletext | Burn\-inTTML | 
| QuickTime Container | Embedded | Burn\-inTTML | 
|   | SCTE\-20 | Burn\-inTTML | 
|   | Ancillary | Burn\-inTTML | 
| Raw Container | SRT | Burn\-inTTML | 
|   | SMI | Burn\-inTTML | 
|   | TTML | Burn\-inTTML | 
|   | STL | Burn\-inTTML | 
|   | SCC | Burn\-inTTML | 
|   | SMI | Burn\-inTTML | 
| MPEG2\-TS Container | Embedded | Burn\-inTTML | 
|   | SCTE\-20 | Burn\-inTTML | 
|   | Teletext | Burn\-inTTML | 
|   | DVB\-Sub | Burn\-in | 

## MP4 Output Container<a name="mp4-output-container"></a>

The following table lists supported output caption formats for this output container, sorted by the input caption container and input caption format\. 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the Quicktime Captions Track
+ Captions in the MXF container VANC data


| Input Caption Container | Input Caption Format | Supported Output Caption Formats | 
| --- | --- | --- | 
| MP4 Container | Embedded | Burn InEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn InEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| MXF Container | Embedded | Burn InEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn InEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Ancillary | Burn InEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Teletext | Burn InEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| QuickTime Container | Embedded | Burn InEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn InEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Ancillary | Burn InEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| Raw Container | SRT | Burn In | 
|   | TTML | Burn In | 
|   | STL | Burn In | 
|   | SCC | Burn InEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SMI | Burn In | 
| MPEG2\-TS Container | Embedded | Burn InEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn InEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Teletext | Burn In | 
|   | DVB\-Sub | Burn In | 

## MPEG2\-TS File Output Container<a name="mpeg2-ts-file-output-container"></a>

The following table lists supported output caption formats for this output container, sorted by the input caption container and input caption format\. 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the Quicktime Captions Track
+ Captions in the MXF container VANC data

**Note**  
AWS Elemental MediaConvert has the following limitations with Teletext in outputs:  
The service doesn't support captions formatting and positioning
You can use only [Teletext level 1\.5](https://en.wikipedia.org/wiki/World_System_Teletext) languages


| Input Caption Container | Input Caption Format | Supported Output Caption Formats | 
| --- | --- | --- | 
| IMF Container Specify the CPL to define your input\.  | IMSC1 text profile |  Burn in DVB\-Sub Teletext  | 
| MP4 Container | Embedded |  Burn\-in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | SCTE\-20 |  Burn\-in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
| MXF Container | Embedded |  Burn\-in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | SCTE\-20 |  Burn\-in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | Ancillary |  Burn\-in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | Teletext |  Burn\-in DVB\-Sub Teletext  | 
| QuickTime Container | Embedded |  Burn\-in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | SCTE\-20 |  Burn\-in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | Ancillary |  Burn\-in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
| Raw Container | SRT |  Burn\-in Teletext  | 
|   | SMI |  Burn\-in DVB\-Sub  | 
|   | TTML |  Burn\-in Teletext DVB\-Sub  | 
|   | STL |  Burn\-in Teletext DVB\-Sub  | 
|   | SCC |  Burn\-in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|   | SMI |  Burn\-in DVB\-Sub  | 
| MPEG2\-TS Container | Embedded | Burn\-inDVB\-SubEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn\-inDVB\-SubEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Teletext |  Burn\-in DVB\-Sub Teletext  | 
|   | DVB\-Sub |  Burn\-in DVB\-Sub  | 

## MXF Output Container<a name="mxf-output-container"></a>

The following table lists supported output caption formats for this output container, sorted by the input caption container and input caption format\. 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the Quicktime Captions Track
+ Captions in the MXF container VANC data


| Input Caption Container | Input Caption Format | Supported Output Caption Formats | 
| --- | --- | --- | 
| IMF Container Specify the CPL to define your input\.  | IMSC1 text profile | Burn in | 
| MP4 Container | Embedded | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| MPEG2\-TS Container | DVB\-Sub | Burn\-inDVB\-Sub | 
|  | Teletext | Burn\-inDVB\-Sub | 
| MXF Container | Ancillary | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| QuickTime Container | Embedded | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Ancillary | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| Raw Container | SRT | Burn\-in | 
|   | TTML | Burn\-in | 
|   | STL | Burn\-in | 
|   | SCC | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SMI | Burn\-in | 
| MPEG2\-TS Container | Embedded | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 

## QuickTime Output Container<a name="quicktime-output-container"></a>

The following table lists supported output caption formats for this output container, sorted by the input caption container and input caption format\. 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the Quicktime Captions Track
+ Captions in the MXF container VANC data


| Input Caption Container | Input Caption Format | Supported Output Caption Formats | 
| --- | --- | --- | 
| IMF Container Specify the CPL to define your input\.  | IMSC1 text profile | Burn in | 
| MP4 Container | Embedded | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| MXF Container | Embedded | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Ancillary | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Teletext | Burn\-in | 
| QuickTime Container | Embedded | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Ancillary | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| Raw Container | SRT | Burn\-in | 
|   | TTML | Burn\-in | 
|   | STL | Burn\-in | 
|   | SCC | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SMI | Burn\-in | 
| MPEG2\-TS Container | Embedded | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Teletext | Burn\-in | 
|   | DVB\-Sub | Burn\-in | 

## No Output Container<a name="no-output-container"></a>

The following table lists supported output caption formats for this output container, sorted by the input caption container and input caption format\. 

**Embedded** captions formats include:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

**Ancillary** captions include:
+ Captions in the Quicktime Captions Track
+ Captions in the MXF container VANC data


| Input Caption Container | Input Caption Format | Supported Output Caption Formats | 
| --- | --- | --- | 
| MP4 Container | Embedded | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| MXF Container | Embedded | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Ancillary | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Teletext | Burn\-in | 
| QuickTime Container | Embedded | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Ancillary | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
| Raw Container | SRT | Burn\-in | 
|   | TTML | Burn\-in | 
|   | STL | Burn\-in | 
|   | SCC | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SMI | Burn\-in | 
| MPEG2\-TS Container | Embedded | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | SCTE\-20 | Burn\-inEmbeddedEmbedded plus SCTE\-20SCTE\-20 plus embedded | 
|   | Teletext | Burn\-in | 
|   | DVB\-Sub | Burn\-in | 