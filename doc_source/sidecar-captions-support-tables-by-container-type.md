# Supported captions workflows, sidecar input captions<a name="sidecar-captions-support-tables-by-container-type"></a>

The following tables show the captions formats you can create in your outputs when your input captions are in a sidecar format\. *Sidecar captions* are captions that you provide as a separate input file from your video\.

To see whether MediaConvert supports your captions workflow, go to the table for your video output container\. Note that MediaConvert doesn't support every possible file extension for each sidecar format\.

**Topics**
+ [Sidecar captions supported in CMAF output container](#sidecar-cmaf-output-container)
+ [Sidecar captions supported in DASH output container](#sidecar-dash-output-container)
+ [Sidecar captions supported in HLS output container](#sidecar-hls-output-container)
+ [Sidecar captions supported in Microsoft Smooth Streaming \(MSS\) output container](#sidecar-mss-output-container)
+ [Sidecar captions supported in MP4 output container](#sidecar-mp4-output-container)
+ [Sidecar captions supported in MPEG2\-TS File output container](#sidecar-mpeg2-ts-output-container)
+ [Sidecar captions supported in MXF output container](#sidecar-mxf-output-container)
+ [Sidecar captions supported in QuickTime output container](#sidecar-quicktime-output-container)
+ [Sidecar captions supported with File output groups](#sidecar-captions-supported-as-standalone-file-in-output)

## Sidecar captions supported in CMAF output container<a name="sidecar-cmaf-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in a sidecar format\. *Sidecar* captions are captions that are in a separate file from your video\.


|  Input captions format  | Supported file extensions |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMSC1 text profile  |  \.xml  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  SCC  |  \.scc  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  SMI  |  \.smi  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  SMPTE\-TT  |  \.ttml, \.xml, \.dfxp  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  SRT  |  \.srt  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  EBU STL  |  \.stl  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  TTML  |  \.ttml, \.xml, \.dfxp  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 
|  WebVTT  |  \.vtt  |  IMSC \(as sidecar \.fmp4\) WebVTT  | 

## Sidecar captions supported in DASH output container<a name="sidecar-dash-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in a sidecar format\. *Sidecar* captions are captions that are in a separate file from your video\.


|  Input captions format  | Supported file extensions |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMSC1 text profile  |  \.xml  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  SCC  |  \.scc  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  SMI  |  \.smi  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  SMPTE\-TT  |  \.ttml, \.xml, \.dfxp  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  SRT  |  \.srt  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  EBU STL  |  \.stl  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  TTML  |  \.ttml, \.xml, \.dfxp  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 
|  WebVTT  |  \.vtt  |  Burn in IMSC \(as sidecar \.fmp4\) IMSC \(as sidecar \.xml\) TTML \(as sidecar \.fmp4\) TTML \(as sidecar \.ttml\)  | 

## Sidecar captions supported in HLS output container<a name="sidecar-hls-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in a sidecar format\. *Sidecar* captions are captions that are in a separate file from your video\.


|  Input captions format  | Supported file extensions |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMSC1 text profile  |  \.xml  |  Burn in WebVTT  | 
|  SCC  |  \.scc  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded WebVTT  | 
|  SMI  |  \.smi  |  Burn in WebVTT  | 
|  SMPTE\-TT  |  \.ttml, \.xml, \.dfxp  |  Burn in WebVTT  | 
|  SRT  |  \.srt  |  Burn in WebVTT  | 
|  EBU STL  |  \.stl  |  Burn in WebVTT  | 
|  TTML  |  \.ttml, \.xml, \.dfxp  |  Burn in WebVTT  | 
|  WebVTT  |  \.vtt  |  Burn in WebVTT  | 



## Sidecar captions supported in Microsoft Smooth Streaming \(MSS\) output container<a name="sidecar-mss-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in a sidecar format\. *Sidecar* captions are captions that are in a separate file from your video\.


|  Input captions format  | Supported file extensions |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMSC1 text profile  |  \.xml  |  Burn in TTML  | 
|  SCC  |  \.scc  |  Burn in TTML  | 
|  SMI  |  \.smi  |  Burn in TTML  | 
|  SMPTE\-TT  |  \.ttml, \.xml, \.dfxp  |  Burn in TTML  | 
|  SRT  |  \.srt  |  Burn in TTML  | 
|  EBU STL  |  \.stl  |  Burn in TTML  | 
|  TTML  |  \.ttml, \.xml, \.dfxp  |  Burn in TTML  | 
|  WebVTT  |  \.vtt  |  Burn in TTML  | 

## Sidecar captions supported in MP4 output container<a name="sidecar-mp4-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in a sidecar format\. *Sidecar* captions are captions that are in a separate file from your video\.


|  Input captions format  | Supported file extensions |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMSC1 text profile  |  \.xml  |  Burn in  | 
|  SCC  |  \.scc  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded  | 
|  SMI  |  \.smi  |  Burn in  | 
|  SMPTE\-TT  |  \.ttml, \.xml, \.dfxp  |  Burn in TTML  | 
|  SRT  |  \.srt  |  Burn in  | 
|  EBU STL  |  \.stl  |  Burn in  | 
|  TTML  |  \.ttml, \.xml, \.dfxp  |  Burn in  | 
|  WebVTT  |  \.vtt  |  Burn in  | 

## Sidecar captions supported in MPEG2\-TS File output container<a name="sidecar-mpeg2-ts-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in a sidecar format\. *Sidecar* captions are captions that are in a separate file from your video\.

 


|  Input captions format  | Supported file extensions |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMSC1 text profile  |  \.xml  |  Burn in Teletext DVB\-Sub  | 
|  SCC  |  \.scc  |  Burn in DVB\-Sub Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded Teletext  | 
|  SMI  |  \.smi  |  Burn in DVB\-Sub  | 
|  SMPTE\-TT  |  \.ttml, \.xml, \.dfxp  |  Burn in Teletext DVB\-Sub  | 
|  SRT  |  \.srt  |  Burn in Teletext  | 
|  EBU STL  |  \.stl  |  Burn in Teletext DVB\-Sub  | 
|  TTML  |  \.ttml, \.xml, \.dfxp  |  Burn in Teletext DVB\-Sub  | 
|  WebVTT  |  \.vtt  |  Burn in Teletext DVB\-Sub  | 

## Sidecar captions supported in MXF output container<a name="sidecar-mxf-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in a sidecar format\. *Sidecar* captions are captions that are in a separate file from your video\.


|  Input captions format  | Supported file extensions |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMSC1 text profile  |  \.xml  |  Burn in Teletext  | 
|  SCC  |  \.scc  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded Teletext  | 
|  SMI  |  \.smi  |  Burn in  | 
|  SMPTE\-TT  |  \.ttml, \.xml, \.dfxp  |  Burn in  | 
|  SRT  |  \.srt  |  Burn in Teletext  | 
|  EBU STL  |  \.stl  |  Burn in Teletext  | 
|  TTML  |  \.ttml, \.xml, \.dfxp  |  Burn in Teletext  | 
|  WebVTT  |  \.vtt  |  Burn in Teletext  | 

## Sidecar captions supported in QuickTime output container<a name="sidecar-quicktime-output-container"></a>

The following table lists supported output captions formats for this output container, when your input captions are in a sidecar format\. *Sidecar* captions are captions that are in a separate file from your video\.


|  Input captions format  | Supported file extensions |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMSC1 text profile  |  \.xml  |  Burn in  | 
|  SCC  |  \.scc  |  Burn in Embedded Embedded plus SCTE\-20 SCTE\-20 plus embedded   | 
|  SMI  |  \.smi  |  Burn in  | 
|  SMPTE\-TT  |  \.ttml, \.xml, \.dfxp  |  Burn in  | 
|  SRT  |  \.srt  |  Burn in  | 
|  EBU STL  |  \.stl  |  Burn in  | 
|  TTML  |  \.ttml, \.xml, \.dfxp  |  Burn in  | 
|  WebVTT  |  \.vtt  |  Burn in  | 

## Sidecar captions supported with File output groups<a name="sidecar-captions-supported-as-standalone-file-in-output"></a>

The following table lists standalone sidecar output captions formats that MediaConvert supports with outputs in the **File** output group\. *Sidecar* captions are captions that are in a separate file from your video\. 

 When you set up these output captions in your job, choose **No container** \(`RAW`\) for **Container**, under **Output settings**\. In your JSON job specification, specify it this way:

```
 {
            "ContainerSettings": {
              "Container": "RAW"
            },
```

**Note**  
You can create sidecar captions outputs only as part of a job that also generates a video output\. 


|  Input captions format  | Supported file extensions |  Supported output captions formats  | 
| --- | --- | --- | 
|  IMSC1 text profile  |  \.xml  |  IMSC \(as sidecar \.xml\) IMSC SRT SMI TTML WebVTT  | 
|  SCC  |  \.scc  |  IMSC \(as sidecar \.xml\) SCC SRT SMI TTML WebVTT  | 
|  SMI  |  \.smi  |  IMSC \(as sidecar \.xml\) SRT SMI TTML WebVTT  | 
|  SMPTE\-TT  |  \.ttml, \.xml, \.dfxp  |  IMSC \(as sidecar \.xml\) SRT SMI TTML WebVTT  | 
|  SRT  |  \.srt  |  IMSC \(as sidecar \.xml\) IMSC SRT SMI TTML WebVTT  | 
|  EBU STL  |  \.stl  |  IMSC \(as sidecar \.xml\) SRT SMI TTML WebVTT  | 
|  TTML  |  \.ttml, \.xml, \.dfxp  |  IMSC \(as sidecar \.xml\) SRT SMI TTML WebVTT  | 
|  WebVTT  |  \.vtt  |  IMSC \(as sidecar \.xml\) SRT SMI TTML WebVTT  | 