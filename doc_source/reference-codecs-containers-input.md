# Supported input codecs and containers<a name="reference-codecs-containers-input"></a>

AWS Elemental MediaConvert accepts input files in the following combinations of codecs and containers\.

**Note**  
For outputs that contain only audio inside the output container, MediaConvert supports a smaller set of input containers and codecs\. For more information, see [Supported codecs and containers for audio\-only outputs](supported-codecs-containers-audio-only.md)\.

## Video<a name="reference-codecs-containers-input-video"></a>

MediaConvert supports the following combinations of input containers and video codecs\.


| Container | Video codecs supported with container | 
| --- | --- | 
| No Container | DV/DVCPRO, AVC \(H\.264\), HEVC \(H\.265\), MPEG\-1, MPEG\-2 | 
| 3G2 | AVC \(H\.264\), H\.263, MPEG\-4 part 2 | 
| 3GP | AVC \(H\.264\), H\.263, MPEG\-4 part 2 | 
| Audio Video Interleave \(AVI\) | Uncompressed, Canopus HQ, DivX/Xvid, DV/DVCPRO | 
| Adobe Flash | AVC \(H\.264\), Flash 9 File, H\.263 | 
| Matroska | AVC \(H\.264\), PCM, MPEG\-2, MPEG\-4 part 2, VC\-1 | 
| IMF | Apple ProRes, JPEG 2000 \(J2K\) | 
| MPEG Transport Streams | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2, VC\-1 | 
| MPEG\-1 System Streams |  MPEG\-1, MPEG\-2 | 
| MPEG\-4 | Uncompressed, AVC Intra 50/100, DivX/Xvid, H\.261, H\.262, H\.263, AVC \(H\.264\), HEVC \(H\.265\), JPEG 2000, MPEG\-2, MPEG\-4 part 2, VC\-1 | 
| MXF | Uncompressed, Apple ProRes \([supported types](supported-types-for-apple-prores-inputs.md)\), AVC Intra 50/100, DNxHD, DV/DVCPRO, DV25, DV50, DVCPro HD, AVC \(H\.264\), JPEG 2000 \(J2K\), MPEG\-2, Panasonic P2, SonyXDCam, SonyXDCam MPEG\-4 Proxy | 
| QuickTime | Uncompressed, Apple ProRes \([supported types](supported-types-for-apple-prores-inputs.md)\), AVC Intra 50/100, DivX/Xvid, DV/DVCPRO, H\.261, H\.262, H\.263, AVC \(H\.264\), HEVC \(H\.265\), JPEG 2000 \(J2K\), MJPEG, MPEG\-2, MPEG\-4 part 2, QuickTime Animation \(RLE\) | 
| WebM | VP8, VP9 | 
| WMV/ASF | VC\-1 | 

**Note**  
MediaConvert doesn't support external reference MOV or MXF input files\.  
MediaConvert doesn't currently support HLS inputs\.

## Audio<a name="reference-codecs-containers-input-audio"></a>

MediaConvert supports the following combinations of input containers and audio codecs\.

**Note**  
For outputs that contain only audio inside the output container, MediaConvert supports a smaller set of input containers and codecs\. For more information, see [Supported codecs and containers for audio\-only outputs](supported-codecs-containers-audio-only.md)\.


| Container | Audio codecs | 
| --- | --- | 
| No Container | PCM | 
| 3G2 | AAC | 
| 3GP | AAC | 
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
| WebM | Opus, Vorbis | 
| WMV/ASF | WMA, WMA2 | 

## Audio\-only<a name="reference-codecs-containers-input-audio-only"></a>

MediaConvert supports the following combinations of input container and codec for audio\-only outputs\.


| Container | Audio Codecs | 
| --- | --- | 
| MPEG\-1 Layer 3 \(\.mp3\) | MP3 | 
| MPEG\-2 TS \(\.ts, m2ts\) | MP2, PCM | 
| MPEG\-4 \(\.mp4\) | AAC | 
| QuickTime \(\.mov\) | PCM | 
| WAV \(\.wav\) | PCM | 