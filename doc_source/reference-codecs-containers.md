# Supported output codecs and containers<a name="reference-codecs-containers"></a>

AWS Elemental MediaConvert supports the following combinations of codecs and containers\.

## Video<a name="reference-codecs-containers-output-video"></a>

MediaConvert supports the following combinations of output containers and video codecs\.


| Container | Codecs supported with container | 
| --- | --- | 
| CMAF | AV1, AVC \(H\.264\), HEVC \(H\.265\) | 
| DASH | AV1, AVC \(H\.264\), HEVC \(H\.265\) | 
| HLS | AVC \(H\.264\), HEVC \(H\.265\) | 
| MPEG\-2 TS | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2 | 
| MPEG\-4 \(\.mp4\) | AV1, AVC \(H\.264\), HEVC \(H\.265\) | 
| MPEG\-4 Flash \(\.f4v\) | AVC \(H\.264\), MPEG\-2 | 
| MXF \(\.mxf\) | MPEG\-2 | 
| QuickTime | AVC \(H\.264\), MPEG\-2, Apple ProRes \([supported types](supported-types-for-apple-prores-outputs.md)\) If your output container is QuickTime and your output video codec is Apple ProRes, you must use AIFF for your output audio codec\.  | 
| Smooth \(ISMV\) | AVC \(H\.264\) | 
| WebM | VP8, VP9 | 
| Raw \(no container\) | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2 | 

**Note**  
MediaConvert doesn't support external reference MOV or MXF input files\.

## Audio<a name="reference-codecs-containers-output-audio"></a>

MediaConvert supports the following combinations of output containers and audio codecs\.

**Note**  
For outputs that contain only audio inside the output container, MediaConvert supports a different set of containers and codecs\. For more information, see [Audio\-only](#audio-only-output)\.


| Container | Codecs supported with container | 
| --- | --- | 
| CMAF | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\) | 
| DASH | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\) | 
| HLS | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\) | 
| MPEG\-2 TS | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\), MP2, PCM/WAV | 
| MPEG\-4 \(\.mp4\) | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\) | 
| MPEG\-4 Flash \(\.f4v\) | AAC | 
| MXF \(\.mxf\) | PCM/WAV | 
| QuickTime | AAC, with H\.264 and MPEG\-2; AIFF, with Apple ProRes; Dolby Digital \(AC3\), with H\.264 and MPEG\-2; Dolby Digital Plus \(EAC3\), with H\.264 and MPEG\-2; WAV \(with H\.264 and MPEG\-2\) | 
| Smooth \(ISMV\) | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\) | 
| WebM | Opus, Vorbis | 
| Raw \(no container\) |  AAC, AIFF, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\), PCM/WAV | 

## Audio\-only<a name="audio-only-output"></a>

MediaConvert supports the following combinations of output container and codec for creating audio\-only outputs\.


| Container | Audio Codecs | 
| --- | --- | 
| HLS \(\.ts\) | AAC, Dolby Digital \(AC3\) | 
| MPEG\-1 Layer 3 \(\.mp3\) | MP3 | 
| MPEG\-2 TS \(\.ts, \.m2ts\) | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\), MP2 | 
| MPEG\-4 \(\.mp4\) | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\) | 