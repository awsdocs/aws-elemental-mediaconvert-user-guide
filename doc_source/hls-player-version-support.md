# HLS player version support<a name="hls-player-version-support"></a>

Most HLS assets that you create with AWS Elemental MediaConvert are compatible with HLS players version 2 and later\. Depending on the features that you use in MediaConvert, some assets require versions of HLS players that are later than version 2, such as versions 3, 4, or 5\. MediaConvert automatically sets the player version metadata based on the features that you enable\.

This list shows the features that might require updated player support:

**Manifest duration format**: HLS output group > Apple HLS group settings > Advanced > Manifest duration format   
When you set your manifest duration format to **Integer**, viewers can play the asset with HLS players version 2 and later\.  
When you set your manifest duration format to **Floating point**, viewers can play the asset with HLS players version 3 and later\.

**Segment control**: HLS output group > Apple HLS group settings > Segment control  
When you set segment control to **Single file**, viewers can play the asset with HLS players version 4 and later\.  
When you set segment control to **Segmented files**, viewers can play the asset with HLS players version 2 and later\.

**Add I\-frame only manifest**: HLS Output group > Output > Advanced > Add I\-frame only manifest  
When you choose **Include**, viewers can play the asset with HLS players version 4 and later\.  
When you choose **Exclude**, viewers can play the asset with HLS players version 2 and later\.

**Audio track type**: HLS Output group > Output > Output Settings > Advanced > Audio track type  
When you choose one of the **Alternate audio** options for any of your audio variants, viewers can play the asset with HLS players version 4 and later\.  
When you choose **Audio\-only variant stream** for **Audio track type** or leave **Audio track type** unselected for all of your audio variants, viewers can play the asset with HLS players version 2 and later\.

**DRM encryption method**: HLS output group > DRM encryption > Encryption method  
When you choose **SAMPLE\-AES** for **DRM encryption**, **Encryption method**, viewers can play the asset with HLS players version 5 and later\.  
When you choose any other value for **DRM encryption**, **Encryption method**, viewers can play the asset with HLS players version 2 and later\.