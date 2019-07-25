# Supported Output Codecs and Containers<a name="reference-codecs-containers"></a>

AWS Elemental MediaConvert supports the following combinations of codecs and containers\.

## Video<a name="reference-codecs-containers-output-video"></a>


| Container | Codecs Supported with Container | 
| --- | --- | 
| CMAF | AVC \(H\.264\), HEVC \(H\.265\) | 
| DASH | AVC \(H\.264\), HEVC \(H\.265\) | 
| HLS | AVC \(H\.264\), HEVC \(H\.265\) | 
| MPEG\-2 TS | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2 | 
| MPEG\-4 \(\.mp4\) | AVC \(H\.264\), HEVC \(H\.265\) | 
| MPEG\-4 Flash \(\.f4v\) | AVC \(H\.264\), MPEG\-2 | 
| MXF \(\.mxf\) | MPEG\-2 | 
| QuickTime | AVC \(H\.264\), MPEG\-2, Apple ProRes If your output container is QuickTime and your output video codec is Apple ProRes, you must use AIFF for your output audio codec\.  | 
| Smooth \(ISMV\) | AVC \(H\.264\) | 
| Raw \(no container\) | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2 | 

**Note**  
MediaConvert doesn't support external reference MOV or MXF input files\.

## Audio<a name="reference-codecs-containers-output-audio"></a>

Supported audio output codecs and containers are listed in the table below\.


| Container | Codecs Supported with Container | 
| --- | --- | 
| CMAF | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\) | 
| DASH | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\) | 
| HLS | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\) | 
| MPEG\-2 TS | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\), MP2 | 
| MPEG\-4 \(\.mp4\) | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\) | 
| MPEG\-4 Flash \(\.f4v\) | AAC | 
| MXF \(\.mxf\) | WAV | 
| QuickTime | AAC, with H\.264 and MPEG\-2; AIFF, with Apple ProRes; Dolby Digital \(AC3\), with H\.264 and MPEG\-2; Dolby Digital Plus \(EAC3\), with H\.264 and MPEG\-2; WAV \(with H\.264 and MPEG\-2\) | 
| Smooth \(ISMV\) | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\) | 
| Raw \(no container\) |  AAC, AIFF, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\), WAV | 

**Note**  
For outputs that contain only audio inside the output container, MediaConvert supports a smaller set of containers and codecs\. For more information, see [Supported Codecs and Containers for Audio\-Only Outputs](supported-codecs-containers-audio-only.md)\.