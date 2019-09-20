# IMSC \(as Part of an IMF Source\)<a name="IMSC-in-MXF"></a>

AWS Elemental MediaConvert supports IMSC as an input captions format either as a sidecar file or as part of an IMF source\. If your input IMSC captions are in a sidecar file, see [IMSC, SCC, SRT, STL, TTML \(Sidecar\)](sidecar-input.md)\.

When your input IMSC captions are part of an IMF source, you don't specify the source file for IMSC captions\. That information is in the CPL file that you specify for your job input\. For restrictions on IMSC support, see [IMSC Captions Support in AWS Elemental MediaConvert](imsc-captions-support.md)\.

**Number of Captions Selectors for IMSC**  
Create one captions selector per track\.

**Track Number**  
Specify which captions you want by providing a track number\. The track numbers correspond to the order that the tracks appear in the CPL file\. For example, if your CPL file lists your French captions first, set **Track number** to **1** to specify the French captions\.

**In Your JSON Job Specification**  
If you use the API or an SDK, you can find these settings in the JSON file of your job\. These settings are under `Inputs`, as in the following example:

```
"Inputs": [

 
      {
        ...
        		
        "CaptionSelectors": {
          "Captions Selector 1": {
            "SourceSettings": {
              "SourceType": "IMSC",
              "TrackSourceSettings": {
                "TrackNumber": 1
              }
            }
          },

          "Captions Selector 2": {
            "SourceSettings": {
              "SourceType": "IMSC",
              "TrackSourceSettings": {
                "TrackNumber": 4
              }
            }
          },
          ...
```