# WebVTT input captions \(as part of an HLS source\)<a name="WebVTT-in-HLS"></a>

AWS Elemental MediaConvert supports WebVTT as an input captions format either as a sidecar file or as part of an HLS source\. If your input WebVTT captions are in a sidecar file, see [IMSC, SCC, SMPTE\-TT, SRT, STL, TTML \(sidecar\) input captions](sidecar-input.md)\.

When your input WebVTT captions are part of a HLS source, you don't need to specify the source WebVTT manifest file for the WebVTT captions\. That information is in the main HLS input file that you specify in your job input\. You will need to enable the **Use HLS Rendition Group** and use the following settings\.

**Number of captions selectors for WebVTT**  
Create one captions selector per WebVTT source\.

**Rendition Group Id**  
Specify which captions group you want by providing a group id\. The group id corresponds to EXT\-X\-MEDIA, GROUP\-ID tag in your HLS manifest\. For example, if your HLS manifest file lists your French captions in a specific group "subs", set **Rendition Group ID** to **subs** to specify the French captions group id\.

**Rendition Name**  
Specify which captions group you want by providing a rendition name\. The rendition name corresponds to EXT\-X\-MEDIA, NAME tag in your HLS manifest\. For example, if your HLS manifest file lists your French captions in a rendition name called "French", set **Rendition Name** to **French** to specify the French captions rendition name\.

**Rendition Language Code**  
Specify which captions group you want by providing an ISO 639\-3 language code\. The language corresponds to EXT\-X\-MEDIA, LANGUAGE tag in your HLS manifest\. For example, if your HLS manifest file lists your French captions in a language code of "FRA", set **Rendition Language Code** to **FRA** to specify the French captions rendition language code\.

**In your JSON job specification**  
If you use the API or an SDK, you can find these settings in the JSON file of your job\. These settings are under `Inputs`, as in the following example:

```
"Inputs": [

 
      {
        ...
        		
"CaptionSelectors": {
  "Caption Selector 1": {
    "SourceSettings": {
      "SourceType": "WebVTT",
      "WebvttHlsSourceSettings": {
        "RenditionGroupId": "subs",
        "RenditionName": "French",
        "RenditionLanguageCode": "FRA"
      }
    }
  }
}
          ...
```