# Supported Output Codecs and Containers<a name="reference-codecs-containers"></a>

MediaConvert supports the following combinations of codecs and containers\.

## Video<a name="reference-codecs-containers-output-video"></a>


| Container | Codecs Supported with Container | 
| --- | --- | 
| MPEG DASH | AVC \(H\.264\), HEVC \(H\.265\) | 
| MPEG\-2 TS | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2 | 
| HLS | AVC \(H\.264\), HEVC \(H\.265\) | 
| Smooth \(ISMV\) | AVC \(H\.264\) | 
| MPEG\-4 \(\.mp4\) | AVC \(H\.264\), HEVC \(H\.265\) | 
| MPEG\-4 Flash \(\.f4v\) | AVC \(H\.264\), MPEG\-2 | 
| QuickTime | AVC \(H\.264\), MPEG\-2, Apple ProRes \(with AIFF audio only\) | 
| MXF \(\.mxf\) | MPEG\-2 | 
| Raw \(no container\) | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2 | 

**Note**  
AWS Elemental MediaConvert doesn't support external reference MOV or MXF input files\.

## Audio<a name="reference-codecs-containers-output-audio"></a>

Supported audio output codecs and containers are listed in the table below\.


| Container | Codecs Supported with Container | 
| --- | --- | 
| MPEG DASH | AAC, Dolby Digital Plus, Dolby Digital | 
| MPEG\-2 TS | AAC, Dolby Digital Plus, Dolby Digital, MP2 | 
| HLS | AAC, Dolby Digital Plus, Dolby Digital  | 
| Smooth \(ISMV | AAC, Dolby Digital Plus, Dolby Digital | 
| MPEG\-4 \(\.mp4\) | AAC, Dolby Digital Plus, Dolby Digital | 
| MPEG\-4 Flash \(\.f4v\) | AAC | 
| QuickTime | AAC \(with H\.264 and MPEG\-2\), AIFF \(with Apple ProRes\), Dolby Digital Plus \(with H\.264 and MPEG\-2\), Dolby Digital \(with H\.264 and MPEG\-2\), WAV \(with H\.264 and MPEG\-2\),  | 
| MXF \(\.mxf\) | WAV | 
| Raw \(no container\) |  AAC, AIFF, Dolby Digital Plus, Dolby Digital, WAV | 
| Audio Only MPEG\-2 TS | AAC, Dolby Digital Plus, Dolby Digital, MP2 | 
| Audio Only MPEG\-4 | AAC, Dolby Digital Plus, Dolby Digital, | 