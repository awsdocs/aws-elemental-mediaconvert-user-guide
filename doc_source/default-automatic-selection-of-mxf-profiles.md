# Default automatic selection of MXF profiles<a name="default-automatic-selection-of-mxf-profiles"></a>

When you choose MXF as your video output container and you keep the default value **Auto** for **MXF profile**, MediaConvert automatically chooses your MXF profile for you and creates your output accordingly\. How MediaConvert makes the MXF profile selection depends on your output video codec\.

**Note**  
MediaConvert supports more MXF profiles through automatic profile selection than it does with manual selection\.

**AVC \(H\.264\), AVC Intra, and VC3**  
For AVC \(H\.264\), AVC Intra, and VC3, MediaConvert selects the Generic OP1a profile, without regard for your output encoding settings\.

**XAVC**  
For XAVC, MediaConvert selects the XAVC profile, without regard for your output encode settings\.

**MPEG\-2**  
For MPEG\-2, MediaConvert chooses SMPTE\-386 D10 when your output encoding characteristics conform to the D10 specification\. Otherwise, MediaConvert selects the XDCAM RDD9 profile\. The following table details the relevant encoding settings and the values that you must set to have MediaConvert automatically select the D10 profile\.

**Note**  
For your output resolution and frame rate, you can specify an allowed value explicitly with the settings **Resolution** and **Frame rate**, or you can choose the value **Follow source** and use an input that has an allowed value\.


| Setting | Allowed values for D10 profile | 
| --- | --- | 
|  Combination of: **Resolution** \(wxh\), **Frame rate**, **Interlace mode**  |  Allowed combinations: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/default-automatic-selection-of-mxf-profiles.html)  | 
|  **GOP size**  |  1 frame  | 
|  **Profile**, for your video codec  |  4:2:2  | 
|  **Syntax** This setting is visible on the console when you choose MXF for your cointainer, MPEG\-2 for your video codec, and 4:2:2 for your codec profile\.  |  D10  | 
|  Number of audio tracks Each output track is represented on the console as one **Audio** tab and in your JSON job specification as a direct child of `AudioDescriptions`\.  |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/default-automatic-selection-of-mxf-profiles.html)  | 
|  Captions type You specify this on the console with the setting **Destination type**\.  |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/default-automatic-selection-of-mxf-profiles.html)  | 

This excerpt from a JSON job specification shows the same settings as you would submit them programmatically:

```
{
  "height": 512,
  "width": 720,
  "codecSettings": {
    "codec": "MPEG2",
    "mpeg2Settings": {
      "bitrate": 30000000,
      "syntax": "D_10",
      "framerateDenominator": 1001,
      "framerateControl": "SPECIFIED",
      "framerateNumerator": 30000,
      "numberBFramesBetweenReferenceFrames": 0,
      "gopSize": 1.0,
      "gopSizeUnits": "FRAMES",
      "codecLevel": "MAIN",
      "codecProfile": "PROFILE_422",
      "rateControlMode": "CBR",
      "interlaceMode": "TOP_FIELD"
    }
  }
}
```