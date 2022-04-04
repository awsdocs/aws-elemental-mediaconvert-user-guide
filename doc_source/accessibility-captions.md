# Settings for accessibility captions<a name="accessibility-captions"></a>

You can mark closed caption tracks as an accessibility aid for those who are hearing impaired\. The following section describes how accessibility captions work in AWS Elemental MediaConvert\.

## HLS and CMAF<a name="accessibility-captions-hls-cmaf-webvtt-imsc"></a>

When you output HLS or CMAF and include an ISMC or WebVTT captions track, you can add accessibility attributes for captions to your output manifest\. MediaConvert adds these attributes according to sections 4\.5 and 4\.6 of the [HLS authoring specification for Apple devices](https://developer.apple.com/documentation/http_live_streaming/hls_authoring_specification_for_apple_devices)\.

When you set **Accessibility subtitles** \(`accessibility`\) to **Enabled** \(`ENABLED`\), MediaConvert adds the following attributes to the captions track in the manifest under `EXT-X-MEDIA`: `CHARACTERISTICS="public.accessibility.describes-spoken-dialog,public.accessibility.describes-music-and-sound"` and `AUTOSELECT="YES"`\.

Keep the default value, **Disabled** \(`DISABLED`\), if the captions track is not intended to provide such accessibility\. MediaConvert will not add the attributes from the previous paragraph\.