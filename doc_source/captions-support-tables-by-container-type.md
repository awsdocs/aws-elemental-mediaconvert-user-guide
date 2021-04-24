# Supported captions workflows, input captions in the same file as video<a name="captions-support-tables-by-container-type"></a>

To look up whether MediaConvert supports your captions workflow, choose the topic from the following list that corresponds to your video output container\. Then find the row that corresponds to your input captions container and format\. Check the supported output captions format column to see the available output captions formats\.

**Topics**
+ [Supported captions in CMAF output container](#cmaf-output-container)
+ [Supported captions in DASH output container](#dash-output-container)
+ [Supported captions in HLS output container](#hls-output-container)
+ [Supported captions in Microsoft Smooth Streaming \(MSS\) output container](#mss-output-container)
+ [Supported captions in MP4 output container](#mp4-output-container)
+ [Supported captions in MPEG2\-TS output container](#mpeg2-ts-file-output-container)
+ [Supported captions in MXF output container](#mxf-output-container)
+ [Supported captions in QuickTime output container](#quicktime-output-container)
+ [Sidecar captions supported with File output groups](#sidecar-captions-supported-as-standalone-file-in-output-from-not-sidecar)

## Supported captions in CMAF output container<a name="cmaf-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in the same container or stream as your video\. This table is sorted by the input captions container and input captions format\. 

If your input captions are in a sidecar format, see [Sidecar captions supported in CMAF output container](sidecar-captions-support-tables-by-container-type.md#sidecar-cmaf-output-container)\. *Sidecar captions* are captions that you provide as a separate input file from your video\. 


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  HLS Container  |  Embedded  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  MP4 Container  |  Embedded  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|    |  SCTE\-20  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  MPEG2\-TS Container  |  Embedded  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|    |  SCTE\-20  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|    |  Teletext  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  MXF Container  |  Embedded  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|    |  Ancillary  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  QuickTime Container  |  Embedded  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|    |  Ancillary  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 

In the preceding table, **Embedded** and **Ancillary** refer to groups of similar captions formats\.

Embedded captions include these formats:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

Ancillary captions include these formats:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## Supported captions in DASH output container<a name="dash-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in the same container or stream as your video\. This table is sorted by the input captions container and input captions format\. 

If your input captions are in a sidecar format, see [Sidecar captions supported in DASH output container](sidecar-captions-support-tables-by-container-type.md#sidecar-dash-output-container)\. *Sidecar captions* are captions that you provide as a separate input file from your video\. 


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  HLS Container  |  Embedded  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\) WebVTT  | 
|  IMF Container  Specify the CPL to define your input\.   |  IMSC1 text profile  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  MP4 Container  |  Embedded  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\) WebVTT  | 
|    |  SCTE\-20  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  MPEG2\-TS Container  | DVB\-Sub |  Burn in  | 
|    |  Embedded  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\) WebVTT  | 
|    |  SCTE\-20  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\) WebVTT  | 
|    |  Teletext  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  MXF Container  |  Embedded  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|    |  SCTE\-20  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|    |  Ancillary  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|    |  Teletext  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  QuickTime Container  |  Embedded  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|    |  SCTE\-20  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|    |  Ancillary  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 

In the preceding table, **Embedded** and **Ancillary** refer to groups of similar captions formats\.

Embedded captions include these formats:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

Ancillary captions include these formats:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## Supported captions in HLS output container<a name="hls-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in the same container or stream as your video\. This table is sorted by the input captions container and input captions format\. 

If your input captions are in a sidecar format, see [Sidecar captions supported in HLS output container](sidecar-captions-support-tables-by-container-type.md#sidecar-hls-output-container)\. *Sidecar captions* are captions that you provide as a separate input file from your video\. 

**Note**  
AWS Elemental MediaConvert has the following limitations with Teletext in outputs:  
The service doesn't support captions formatting and positioning
You can use only [Teletext level 1\.5](https://en.wikipedia.org/wiki/World_System_Teletext) languages


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  HLS Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|  IMF Container  Specify the CPL to define your input\.   |  IMSC1 text profile  |  WebVTT  | 
|  MP4 Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|  MPEG2\-TS Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|    |  Teletext  |  Burn in WebVTT  | 
|    | DVB\-Sub |  Burn in  | 
|  MXF Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|    |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|    |  Teletext  |  Burn in  | 
|  QuickTime Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|    |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 

In the preceding table, **Embedded** and **Ancillary** refer to groups of similar captions formats\.

Embedded captions include these formats:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

Ancillary captions include these formats:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data



## Supported captions in Microsoft Smooth Streaming \(MSS\) output container<a name="mss-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in the same container or stream as your video\. This table is sorted by the input captions container and input captions format\. 

If your input captions are in a sidecar format, see [Sidecar captions supported in Microsoft Smooth Streaming \(MSS\) output container](sidecar-captions-support-tables-by-container-type.md#sidecar-mss-output-container)\. *Sidecar captions* are captions that you provide as a separate input file from your video\. 


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  HLS Container  |  Embedded  |  Burn in TTML  | 
|  MP4 Container  |  Embedded  |  Burn in TTML  | 
|    |  SCTE\-20  |  Burn in TTML  | 
|  MPEG2\-TS Container  |  Embedded  |  Burn in TTML  | 
|    |  SCTE\-20  |  Burn in TTML  | 
|    |  Teletext  |  Burn in TTML  | 
|    | DVB\-Sub |  Burn in  | 
|  MXF Container  |  Embedded  |  Burn in TTML  | 
|    |  SCTE\-20  |  Burn in TTML  | 
|    |  Ancillary  |  Burn in TTML  | 
|    |  Teletext  |  Burn in TTML  | 
|  QuickTime Container  |  Embedded  |  Burn in TTML  | 
|    |  SCTE\-20  |  Burn in TTML  | 
|    |  Ancillary  |  Burn in TTML  | 

In the preceding table, **Embedded** and **Ancillary** refer to groups of similar captions formats\.

Embedded captions include these formats:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

Ancillary captions include these formats:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## Supported captions in MP4 output container<a name="mp4-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in the same container or stream as your video\. This table is sorted by the input captions container and input captions format\. 

If your input captions are in a sidecar format, see [Sidecar captions supported in MP4 output container](sidecar-captions-support-tables-by-container-type.md#sidecar-mp4-output-container)\. *Sidecar captions* are captions that you provide as a separate input file from your video\. 


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  HLS Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  MP4 Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  MPEG2\-TS Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  Teletext  |  Burn in  | 
|    | DVB\-Sub |  Burn in  | 
|  MXF Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  Teletext  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  QuickTime Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 

In the preceding table, **Embedded** and **Ancillary** refer to groups of similar captions formats\.

Embedded captions include these formats:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

Ancillary captions include these formats:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## Supported captions in MPEG2\-TS output container<a name="mpeg2-ts-file-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in the same container or stream as your video\. This table is sorted by the input captions container and input captions format\. 

If your input captions are in a sidecar format, see [Sidecar captions supported in MPEG2\-TS File output container](sidecar-captions-support-tables-by-container-type.md#sidecar-mpeg2-ts-output-container)\. *Sidecar captions* are captions that you provide as a separate input file from your video\. 

 

**Note**  
AWS Elemental MediaConvert has the following limitations with Teletext in outputs:  
The service doesn't support captions formatting and positioning
You can use only [Teletext level 1\.5](https://en.wikipedia.org/wiki/World_System_Teletext) languages


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  HLS Container  |  Embedded  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  IMF Container  Specify the CPL to define your input\.   |  IMSC1 text profile  |  Burn in DVB\-Sub Teletext  | 
|  MPEG2\-TS Container  |  Embedded  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded Teletext  | 
|    |  SCTE\-20  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  Teletext  |  Burn in DVB\-Sub Teletext  | 
|    | DVB\-Sub |  Burn in DVB\-Sub  | 
|  MP4 Container  |  Embedded  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded Teletext  | 
|    |  SCTE\-20  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  MXF Container  |  Embedded  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded Teletext  | 
|    |  SCTE\-20  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  Ancillary  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  Teletext  |  Burn in DVB\-Sub Teletext  | 
|  QuickTime Container  |  Embedded  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  SCTE\-20  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  Ancillary  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 

In the preceding table, **Embedded** and **Ancillary** refer to groups of similar captions formats\.

Embedded captions include these formats:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

Ancillary captions include these formats:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## Supported captions in MXF output container<a name="mxf-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in the same container or stream as your video\. This table is sorted by the input captions container and input captions format\. 

If your input captions are in a sidecar format, see [Sidecar captions supported in MXF output container](sidecar-captions-support-tables-by-container-type.md#sidecar-mxf-output-container)\. *Sidecar captions* are captions that you provide as a separate input file from your video\. 

**Note**  
AWS Elemental MediaConvert has the following limitations with Teletext in outputs:  
The service doesn't support captions formatting and positioning
You can use only [Teletext level 1\.5](https://en.wikipedia.org/wiki/World_System_Teletext) languages


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  HLS Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|  IMF Container  Specify the CPL to define your input\.   |  IMSC1 text profile  |  Burn in  | 
|  MP4 Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded Teletext  | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  MPEG2\-TS Container  | DVB\-Sub |  Burn in  | 
|    |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded Teletext  | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  |  Teletext  |  Burn in Teletext  | 
|  MXF Container  |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  |  Embedded  |  Embedded Teletext  | 
|  QuickTime Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|    |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 

In the preceding table, **Embedded** and **Ancillary** refer to groups of similar captions formats\.

Embedded captions include these formats:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

Ancillary captions include these formats:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## Supported captions in QuickTime output container<a name="quicktime-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in the same container or stream as your video\. This table is sorted by the input captions container and input captions format\. 

If your input captions are in a sidecar format, see [Sidecar captions supported in QuickTime output container](sidecar-captions-support-tables-by-container-type.md#sidecar-quicktime-output-container)\. *Sidecar captions* are captions that you provide as a separate input file from your video\. 


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  HLS Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|  IMF Container  Specify the CPL to define your input\.   |  IMSC1 text profile  |  Burn in  | 
|  MP4 Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|  MPEG2\-TS Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|    |  Teletext  |  Burn in  | 
|    |  DVB\-Sub  |  Burn in  | 
|  MXF Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|    |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|    |  Teletext  |  Burn in  | 
|  QuickTime Container  |  Embedded  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|    |  SCTE\-20  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|    |  Ancillary  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 

In the preceding table, **Embedded** and **Ancillary** refer to groups of similar captions formats\.

Embedded captions include these formats:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

Ancillary captions include these formats:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data

## Sidecar captions supported with File output groups<a name="sidecar-captions-supported-as-standalone-file-in-output-from-not-sidecar"></a>

The following table lists standalone sidecar output captions formats that MediaConvert supports with outputs in the **File** output group\. *Sidecar* captions are captions that are in a separate file from your video\. 

If your input captions are in a sidecar format, see [Sidecar captions supported with File output groups](sidecar-captions-support-tables-by-container-type.md#sidecar-captions-supported-as-standalone-file-in-output)\. *Sidecar captions* are captions that you provide as a separate input file from your video\. 

When you set up these output captions in your job, choose **No container** \(`RAW`\) for **Container**, under **Output settings**\. In your JSON job specification, specify it this way:

```
 {
            "ContainerSettings": {
              "Container": "RAW"
            },
```

**Note**  
You can create sidecar captions outputs only as part of a job that also generates a video output\. 


|  Input captions container  |  Input captions format  |  Supported output captions formats  | 
| --- | --- | --- | 
|  HLS Container  |  Embedded  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|  MP4 Container  |  Embedded  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|    |  SCTE\-20  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|  MPEG2\-TS Container  |  Embedded  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|    |  SCTE\-20  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|    |  Teletext  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|  MXF Container  |  Embedded  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|    |  SCTE\-20  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|    |  Ancillary  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|    |  Teletext  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|  QuickTime Container  |  Embedded  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|    |  SCTE\-20  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|    |  Ancillary  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 

In the preceding table, **Embedded** and **Ancillary** refer to groups of similar captions formats\.

Embedded captions include these formats:
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

Ancillary captions include these formats:
+ Captions in the QuickTime Captions Track
+ Captions in the MXF container VANC data