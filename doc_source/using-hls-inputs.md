# Using HLS inputs with AWS Elemental MediaConvert<a name="using-hls-inputs"></a>

When your input to MediaConvert is an HLS package, specify either a parent or child manifest for **Input file URL** \(`[FileInput](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-input-fileinput)`\)\. When the manifest is a parent that lists multiple child manifests, MediaConvert uses the child manifest with the highest bandwidth as the input source\.

## Features compatible with HLS inputs<a name="compatible-features"></a>

With HLS inputs, you can use the following input features:
+ Input clipping
+ Input stitching
+ Image insertion
+ Embedded input captions selectors

## Feature restrictions with HLS inputs<a name="hls-feature-restrictions"></a>

When your input is an HLS package, your job is restricted in these ways:
+ Your input package must conform to the requirements listed in [HLS input package requirements](#hls-input-package-requirements)\.
+ Your input segments can't be encrypted with DRM\. For example, your inputs can't be encrypted with Apple FairPlay DRM\.
+ You can use only embedded input captions\.

## HLS input package requirements<a name="hls-input-package-requirements"></a>

Your input HLS package must conform to the following requirements:
+ The video container for your media segments must be MPEG\-2 TS\.
+ The compatibility version of the manifest file \(specified by `EXT-X-VERSION`\) must be 4 or smaller\.
+ The manifest file must stay the same after you submit your job\. That is, the manifest must have the tag `EXT-X-ENDLIST` or it must have the `EXT-X-PLAYLIST-TYPE` value set to VOD\.
+ If the manifest uses `EXT-X-BYTERANGE`, the start of the first subrange must be 0 and the following subrange segments must continue the former one\.
+ If the input has discontinuities, they must start at the beginning of a segment\. That is, the input can't have discontinuities in the subrange of a segment\.
+ The manifest can't use any of the following tags:
  + `EXT-X-KEY`
  + `EXT-X-PROGRAM-DATE-TIME`
  + `EXT-X-DATERANGE`
  + `EXT-X-I-FRAMES-ONLY`
  + `EXT-X-I-FRAME-STREAM-INF`
  + `EXT-X-SESSION-DATA`
  + `EXT-X-SESSION-KEY`
  + `EXT-X-INDEPENDENT-SEGMENTS`
  + `EXT-X-START`
+ When your job uses accelerated transcoding, your input HLS package must conform to this additional requirement: The duration in `EXTINF` must be specified using a decimal floating\-point, with enough accuracy to avoid perceptible errors when segment durations are accumulated\.

## Using alternate audio renditions<a name="using-alternate-audio-renditions"></a>

With HLS rendition groups, you can use the audio selector settings to indicate which alternate audio rendition you want MediaConvert to use\. To be eligible for selection, your alternate audio renditions must conform to the following requirements:
+ The renditions must be included in `EXT-X-MEDIA` tags in the input parent manifest\.
+ The `EXT-X-MEDIA` tags must contain a unique combination of GROUP\-ID, NAME, and LANGUAGE values\.\.
+ Audio must be in one of the following supported audio codecs: AAC, Dolby Digital \(AC3\), Dolby Digital Plus \(EAC3\), or MP3\.
+ The child mainfest for your alternate audio rendition must be included in the parent manifest that you used for your Input file URL \(FileInput\)

 When you specify audio selector settings to identify an alternate audio rendition, the audio selector looks for a matching `EXT-X-MEDIA` tag in the parent manifest\.

You can use one or more selector settings at a time\. For example, given the following `EXT-X-MEDIA` tags, you can identify the audio rendition by the name \(RenditionName\) or language \(RenditionLangageCode\) because these are both unique values across the tags\.

`#EXT-X-MEDIA:TYPE=AUDIO,GROUP-ID="audio",CHANNELS="2",NAME="English",LANGUAGE="eng",DEFAULT=YES,AUTOSELECT=YES,URI="english_audio.m3u8"` 

`#EXT-X-MEDIA:TYPE=AUDIO,GROUP-ID="audio",CHANNELS="2",NAME="Japanese",LANGUAGE="jpn",DEFAULT=NO,AUTOSELECT=NO,URI="japanese_audio.m3u8"`

However, because the group ID \(RenditionGroupID\) is the same for both tags, you can't use that alone to identify an audio rendition\. You must use the group ID in combination with another value from the `EXT-X-MEDIA` tag to identify the audio rendition that you want MediaConvert to use\.

If you don't specify audio selector settings, the audio selector looks for audio that's muxed into the video segments\. If the video segments don't contain audio, the audio selector uses the first alternate audio rendition from the input parent manifest\.