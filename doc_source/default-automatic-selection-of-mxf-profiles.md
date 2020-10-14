# Default automatic selection of MXF profiles<a name="default-automatic-selection-of-mxf-profiles"></a>

When you choose MXF as your video output container and you keep the default value **Auto** for **MXF profile**, MediaConvert automatically chooses your MXF profile for you and creates your output accordingly\. MediaConvert makes the MXF profile selection based on your output video codec and resolution\. The following table shows which profile the service assigns for each combination\.

**Note**  
MediaConvert supports more MXF profiles through automatic profile selection than it does with manual selection\.


| When you choose this video codec\.\.\. | and a resolution in this category\.\.\. | MediaConvert chooses this MXF profile\. | 
| --- | --- | --- | 
| MPEG\-2 | HD | XDCAM RDD9 | 
| MPEG\-2 | SD | SMPTE\-386 D10 | 
| AVC Intra | HD | Generic OP1a | 
| AVC Intra | SD | Generic OP1a | 
| VC\-3 | HD | Generic OP1a | 
| VC\-3 | SD | Generic OP1a | 