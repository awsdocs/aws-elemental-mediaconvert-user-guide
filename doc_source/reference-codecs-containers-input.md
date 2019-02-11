# Supported Input Codecs and Containers<a name="reference-codecs-containers-input"></a>

MediaConvert accepts input files in the following combinations of codecs and containers\.

**Note**  
MediaConvert doesn't currently support HLS input\.

## Video<a name="reference-codecs-containers-input-video"></a>

Supported video input codecs and containers are listed in the table below\.


| Container | Video Codecs Supported with Container | 
| --- | --- | 
| No Container | DV/DVCPRO, AVC \(H\.264\), HEVC \(H\.265\), MPEG\-1, MPEG\-2 | 
| Audio Video Interleave | Uncompressed, DivX/Xvid, DV/DVCPRO | 
| Adobe® Flash® | Flash® 9 File, H\.263, AVC \(H\.264\) | 
| Matroska | AVC \(H\.264\), MPEG\-2, MPEG\-4 part 2, VC\-1 | 
| IMF | JPEG 2000 \(J2K\) | 
| MPEG Transport Streams | AVC \(H\.264\), HEVC \(H\.265\), MPEG\-2, VC\-1 | 
| MPEG\-1 System Streams |  MPEG\-1, MPEG\-2 | 
| MPEG\-4 | Uncompressed, AVC Intra 50/100, DivX/Xvid, H\.261, H\.262, H\.263, AVC \(H\.264\), HEVC \(H\.265\), JPEG 2000, MJPEG, MPEG\-2, MPEG\-4 part 2, VC\-1 | 
| MXF | Uncompressed, AVC Intra 50/100, DNxHD, DV/DVCPRO, DV25, DV50, DVCPro HD, AVC \(H\.264\), JPEG 2000 \(J2K\), MPEG\-2, Panasonic P2, SonyXDCam, SonyXDCam MPEG\-4 Proxy | 
| QuickTime® | Uncompressed, Apple ProRes, AVC Intra 50/100, DivX/Xvid, DV/DVCPRO, H\.261, H\.262, H\.263, AVC \(H\.264\), JPEG 2000 \(J2K\), MJPEG, MPEG\-2, MPEG\-4 part 2 | 
| WMV/ASF | VC\-1 | 

**Note**  
AWS Elemental MediaConvert doesn't support external reference MOV or MXF input files\.

## Audio<a name="reference-codecs-containers-input-audio"></a>

Supported audio input codecs and containers are listed in the table below\.


| Container | Audio Codecs | 
| --- | --- | 
| No Container | 
| Audio Video Interleave | Dolby® Digital, Dolby® Digital Plus™, Dolby® E frames carried in PCM streams, MPEG Audio, PCM | 
| Adobe® Flash® | AAC | 
| IMF | PCM | 
| Matroska | AAC, Dolby® Digital, Dolby® Digital Plus™, WMA, WMA2 | 
| MPEG Transport Streams | AAC, AIFF, Dolby® Digital, Dolby® Digital Plus™, Dolby® E frames carried in PCM streams, MPEG Audio, PCM, WMA, WMA2 | 
| MPEG\-1 System Streams | AAC, AIFF, Dolby® Digital, Dolby® Digital Plus™, MPEG, Audio PCM | 
| MPEG\-4 | AAC, Dolby® Digital, Dolby® Digital Plus™, PCM, WMA, WMA2 | 
| MXF | AAC, AIFF, Dolby® E frames carried in PCM streams, MPEG Audio, PCM | 
| QuickTime® | AAC | 
| WMV/ASF | WMA, WMA2 | 