# Captions Support Tables by Output Container Type<a name="captions-support-tables-by-container-type"></a>

**Topics**
+ [CMAF Output Container](#cmaf-output-container)
+ [DASH Output Container](#dash-output-container)
+ [HLS Output Container](#hls-output-container)
+ [MS Smooth \(MSS\) Output Container](#mss-output-container)
+ [MP4 Output Container](#mp4-output-container)
+ [MPEG2\-TS File Output Container](#mpeg2-ts-file-output-container)
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
| MP4 Container | Embedded | Web\-VTT | 
| MXF Container | Embedded | Web\-VTT | 
|   | Ancillary | Web\-VTT | 
| QuickTime Container | Embedded | Web\-VTT | 
|   | Ancillary | Web\-VTT | 
| Raw Container | SRT | Web\-VTT | 
|   | TTML | Web\-VTT | 
|   | STL | Web\-VTT | 
|   | SCC | Web\-VTT | 
| MPEG2\-TS Container | Embedded | Web\-VTT | 
|   | Teletext | Web\-VTT | 

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
| MP4 Container | Embedded | Burn inTTML | 
| MXF Container | Embedded | Burn inTTML | 
|   | Ancillary | Burn inTTML | 
|   | Teletext | Burn inTTML | 
| QuickTime Container | Embedded | Burn inTTML | 
|   | Ancillary | Burn inTTML | 
| Raw Container | SRT | Burn inTTML | 
|   | TTML | Burn inTTML | 
|   | STL | Burn inTTML | 
|   | SCC | Burn inTTML | 
| MPEG2\-TS Container | Embedded | Burn inTTML | 
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
| MP4 Container | Embedded |  Burn\-in Embedded Web\-VTT  | 
| MXF Container | Embedded |  Burn\-in Embedded Web\-VTT  | 
|   | Ancillary |  Burn\-in Embedded Web\-VTT  | 
|   | Teletext |  Burn in TTML  | 
| QuickTime Container | Embedded |  Burn\-in Embedded Web\-VTT  | 
|   | Ancillary |  Burn\-in Embedded Web\-VTT  | 
| Raw Container | SRT |  Burn\-in Web\-VTT  | 
|   | TTML |  Burn\-in Web\-VTT  | 
|   | STL |  Burn\-in Web\-VTT  | 
|   | SCC |  Burn\-in Embedded Web\-VTT  | 
| MPEG2\-TS Container | Embedded |  Burn\-in Embedded Web\-VTT  | 
|   | Teletext |  Burn\-in Web\-VTT  | 
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
| MP4 Container | Embedded | Burn\-inTTML | 
| MXF Container | Embedded | Burn\-inTTML | 
|   | Ancillary | Burn\-inTTML | 
|   | Teletext | Burn\-inTTML | 
| QuickTime Container | Embedded | Burn\-inTTML | 
|   | Ancillary | Burn\-inTTML | 
| Raw Container | SRT | Burn\-inTTML | 
|   | SMI | Burn\-inTTML | 
|   | TTML | Burn\-inTTML | 
|   | STL | Burn\-inTTML | 
|   | SCC | Burn\-inTTML | 
| MPEG2\-TS Container | Embedded | Burn\-inTTML | 
|   | Teletext | Burn\-inTTML | 
|   | DVB\-Sub |   | 

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
| MP4 Container | Embedded | Burn InEmbedded | 
| MXF Container | Embedded | Burn InEmbedded | 
|   | Ancillary | Burn InEmbedded | 
|   | Teletext | Burn InEmbedded | 
| QuickTime Container | Embedded | Burn InEmbedded | 
|   | Ancillary | Burn InEmbedded | 
| Raw Container | SRT | Burn In | 
|   | TTML | Burn In | 
|   | STL | Burn In | 
|   | SCC | Burn InEmbedded | 
| MPEG2\-TS Container | Embedded | Burn InEmbedded | 
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
| MP4 Container | Embedded |  Burn\-in DVB\-Sub Embedded  | 
| MXF Container | Embedded |  Burn\-in DVB\-Sub Embedded  | 
|   | Ancillary |  Burn\-in DVB\-Sub Embedded  | 
|   | Teletext |  Burn\-in DVB\-Sub Teletext  | 
| QuickTime Container | Embedded |  Burn\-in DVB\-Sub Embedded  | 
|   | Ancillary |  Burn\-in DVB\-Sub Embedded  | 
| Raw Container | SRT |  Burn\-in Teletext  | 
|   | SMI |  Burn\-in DVB\-Sub  | 
|   | TTML |  Burn\-in Teletext DVB\-Sub  | 
|   | STL |  Burn\-in Teletext DVB\-Sub  | 
|   | SCC |  Burn\-in DVB\-Sub Embedded  | 
| MPEG2\-TS Container | Embedded | Burn\-inDVB\-SubEmbedded | 
|   | Teletext |  Burn\-in DVB\-Sub Teletext  | 
|   | DVB\-Sub |  Burn\-in DVB\-Sub  | 

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
| MP4 Container | Embedded | Burn\-inEmbedded | 
| MXF Container | Embedded | Burn\-inEmbedded | 
|   | Ancillary | Burn\-inEmbedded | 
|   | Teletext | Burn\-in | 
| QuickTime Container | Embedded | Burn\-inEmbedded | 
|   | Ancillary | Burn\-inEmbedded | 
| Raw Container | SRT | Burn\-in | 
|   | TTML | Burn\-in | 
|   | STL | Burn\-in | 
|   | SCC | Burn\-inEmbedded | 
| MPEG2\-TS Container | Embedded | Burn\-inEmbedded | 
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
| MP4 Container | Embedded | Burn\-inEmbedded | 
| MXF Container | Embedded | Burn\-inEmbedded | 
|   | Ancillary | Burn\-inEmbedded | 
|   | Teletext | Burn\-in | 
| QuickTime Container | Embedded | Burn\-inEmbedded | 
|   | Ancillary | Burn\-inEmbedded | 
| Raw Container | SRT | Burn\-in | 
|   | TTML | Burn\-in | 
|   | STL | Burn\-in | 
|   | SCC | Burn\-inEmbedded | 
| MPEG2\-TS Container | Embedded | Burn\-inEmbedded | 
|   | Teletext | Burn\-in | 
|   | DVB\-Sub | Burn\-in | 