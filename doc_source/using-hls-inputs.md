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
+ The manifest file must stay the same after you submit your job\. That is, the manifest must have the tag `EXT-X-ENDLIST` or it must have the `EXT-X-PLAYLIST-TYPE` value set to Video On Demand \(VOD\)\.
+ If the manifest uses `EXT-X-BYTERANGE`, the start of the first subrange must be 0 and the following subrange segments must continue the former one\.
+ If the input has discontinuities, they must start at the beginning of a segment\. That is, the input can't have discontinuities in the subrange of a segment\.
+ The package must not use alternative renditions\. That is, the manifest can't use the `EXT-X-MEDIA` tag, and any audio in your input must be in the same media segments as the video\.
+ The manifest can't use any of the following tags:
  + `EXT-X-KEY`
  + `EXT-X-MEDIA`
  + `EXT-X-PROGRAM-DATE-TIME`
  + `EXT-X-DATERANGE`
  + `EXT-X-I-FRAMES-ONLY`
  + `EXT-X-I-FRAME-STREAM-INF`
  + `EXT-X-SESSION-DATA`
  + `EXT-X-SESSION-KEY`
  + `EXT-X-INDEPENDENT-SEGMENTS`
  + `EXT-X-START`
+ When your job uses accelerated transcoding, your input HLS package must conform to this additional requirement: The duration in `EXTINF` must be specified using a decimal floating\-point, with enough accuracy to avoid perceptible errors when segment durations are accumulated\.