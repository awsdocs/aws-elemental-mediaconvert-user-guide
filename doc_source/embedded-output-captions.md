# CEA/EIA\-608 and CEA/EIA\-708 \(embedded\) output captions<a name="embedded-output-captions"></a>

## Where to specify the captions<a name="where-embedded-output-captions"></a>

Put your captions in the same output group and the same output as your video\.

## How to specify multiple captions tracks<a name="multilang-embedded-output-captions"></a>
+ If your input captions format is embedded \(that is, you are passing through embedded\-to\-embedded\), you need to create only one group of captions settings\. The captions selector that you choose under **Captions source** includes all tracks from the input\.
+ If your input captions are two SCC files, you can create output captions as two output captions channels that are embedded in your output video stream\. For more information, see [Converting dual SCC input files to embedded captions](converting-dual-scc-input-files-to-embedded-captions.md)\.
+ If your input captions are not embedded or SCC, you can include only one captions track per output\. In each output, include one group of captions settings\. Under **Captions source**, choose the selector that is set up for the track that you want to include\.

## Embedded and ancillary captions in MXF outputs<a name="embedded-and-ancillary-captions-in-mxf-outputs"></a>

Whether your MXF output can contain ancillary captions depends on the MXF profile:
+ MXF XDCAM HD: This MXF profile specifies ancillary data in the smpte 436 track\. With these outputs, MediaConvert copies your embedded captions to the smpte 436 ancillary track in addition to including it in the video stream\.
+ MXF D\-10: This MXF profile specification doesn't allow for ancillary data\. Therefore, your MXF D\-10 outputs only have captions embedded in the video stream\.

MediaConvert determines an output's MXF profile based on the values for the following encoding settings:
+ Resolution
+ Frame rate
+ Video codec profile
+ Interlace mode

For information about which values for these settings are valid for which MXF profile, see the relevant specifications\. For XDCAM HD, see [RDD 9:2009 \- SMPTE Standard Doc \- MXF Interoperability Specification of Sony MPEG Long GOP Products](https://ieeexplore.ieee.org/document/7290306) in the IEEE Xplore Digital Library\. For MXF D\-10, see [ST 356:2001 \- SMPTE Standard \- For Television — Type D\-10 Stream Specifications — MPEG\-2 4:2:2P @ ML for 525/60 and 625/50](https://ieeexplore.ieee.org/document/7290684)\.