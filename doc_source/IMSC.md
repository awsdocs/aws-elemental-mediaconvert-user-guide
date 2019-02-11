# IMSC \(as Part of an IMF Source\)<a name="IMSC"></a>

AWS Elemental MediaConvert supports IMSC as an input captions format only when it's part of an IMF source\. Therefore, you don't specify the source file for IMSC captions\. That information is in the CPL file that you specify for your job input\.

**Note**  
AWS Elemental MediaConvert doesn't support IMSC as a sidecar file\.

**Number of Captions Selectors for IMSC**  
Create one captions selector per track\. In each selector, specify the subtitle track that you want by providing a track number\.

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

          "Captions Selector 2": {
            "SourceSettings": {
              "SourceType": "IMSC",
              "TrackSourceSettings": {
                "TrackNumber": 4
              }
```