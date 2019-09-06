# Supported Input Codecs and Containers<a name="reference-codecs-containers-input"></a>

AWS Elemental MediaConvert accepts input files in the following combinations of codecs and containers\.

**Note**  
For outputs that contain only audio inside the output container, MediaConvert supports a smaller set of input containers and codecs\. For more information, see [Supported Codecs and Containers for Audio\-Only Outputs](supported-codecs-containers-audio-only.md)\.

## Video<a name="reference-codecs-containers-input-video"></a>

Supported video input codecs and containers are listed in the following table\.


| Container | Video Codecs Supported with Container | 
| --- | --- | 
| No Container | DV/DVCPRO, AVC \(H\.264\), HEVC \(H\.265\), MPEG\-1, MPEG\-2 | 
| Audio Video Interleave \(AVI\) | Uncompressed, Canopus HQ, DivX/Xvid, DV/DVCPRO | 
| Adobe Flash | AVC \(H\.264\), Flash 9 File, H\.263 | 
| Matroska | AVC \(H\.264\), PCM, MPEG\-2, MPEG\-4 part 2, VC\-1 | 
| IMF | Apple ProRes, JPEG 2000 \(J2K\) | 
| MPEG Transport Streams | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2, VC\-1 | 
| MPEG\-1 System Streams |  MPEG\-1, MPEG\-2 | 
| MPEG\-4 | Uncompressed, AVC Intra 50/100, DivX/Xvid, H\.261, H\.262, H\.263, AVC \(H\.264\), HEVC \(H\.265\), JPEG 2000, MJPEG, MPEG\-2, MPEG\-4 part 2, VC\-1 | 
| MXF | Uncompressed, Apple ProRes, AVC Intra 50/100, DNxHD, DV/DVCPRO, DV25, DV50, DVCPro HD, AVC \(H\.264\), JPEG 2000 \(J2K\), MPEG\-2, Panasonic P2, SonyXDCam, SonyXDCam MPEG\-4 Proxy | 
| QuickTime | Uncompressed, Apple ProRes, AVC Intra 50/100, DivX/Xvid, DV/DVCPRO, H\.261, H\.262, H\.263, AVC \(H\.264\), JPEG 2000 \(J2K\), MJPEG, MPEG\-2, MPEG\-4 part 2 | 
| WebM | VP8, VP9 | 
| WMV/ASF | VC\-1 | 

**Note**  
MediaConvert doesn't support external reference MOV or MXF input files\.  
MediaConvert doesn't currently support HLS inputs\.

## Audio<a name="reference-codecs-containers-input-audio"></a>

Supported audio input codecs and containers are listed in the following table\.


| Container | Audio Codecs | 
| --- | --- | 
| No Container | PCM | 
| Audio Video Interleave \(AVI\) | Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\), Dolby E frames carried in PCM streams, MP3, MPEG Audio, PCM | 
| Adobe Flash | AAC | 
| IMF | PCM | 
| Matroska | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\), WMA, WMA2 | 
| MPEG Transport Streams | AAC, AIFF, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\), Dolby E frames carried in PCM streams, MPEG Audio, PCM, WMA, WMA2 | 
| MPEG\-1 System Streams | AAC, AIFF, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\), MPEG, Audio PCM | 
| MPEG\-1 Layer 3 \(MP3\) | MP3 | 
| MPEG\-4 | AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\), PCM, WMA, WMA2 | 
| MXF | AAC, AIFF, Dolby E frames carried in PCM streams, MPEG Audio, PCM | 
| QuickTime | AAC, MP3, PCM | 
| WebM | Vorbis | 
| WMV/ASF | WMA, WMA2 | 