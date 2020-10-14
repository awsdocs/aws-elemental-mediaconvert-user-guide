# Working with Nielsen to do audio watermarking in AWS Elemental MediaConvert outputs<a name="nielsen-watermarking"></a>

Nielsen is a company that tracks how often video assets are watched by viewers\. One form of that tracking uses tones in a media asset's audio that are audible to machines but not humans\. These tones are encoded directly in the audio stream and can also be cued in the metadata\. To use this Nielsen audio watermarking with MediaConvert, you must first establish a partnership with Nielsen\.

MediaConvert supports Nielsen audio watermarking in these ways:
+ *PCM to ID3 watermarking*: With PCM to ID3 watermarking, MediaConvert translates watermarking that already exists in your input audio stream to markers in your output's ID3 metadata\.
+ *Non\-linear watermarking*: With non\-linear watermarking, MediaConvert inserts integers, called *TICs*, into the PCM audio stream of the asset\. At the locations of these TICs, MediaConvert also encodes audio tones\.

  With non\-linear watermarking, your input must start without watermarking\. AWS Elemental MediaConvert receives the TICs from a Nielsen SID/TIC server that you set up in the AWS Cloud\.

**Note**  
If you want both types of watermarking, you must run your job twice\. First create an output with non\-linear watermarking, and then use that output as input to the next job to add ID3 watermarking from your PCM stream\. You can't enable both kinds of watermarking in a single job\.

**Topics**
+ [Setting up your MediaConvert job for PCM to ID3 metadata](setting-up-pcm-to-id3-metadata.md)
+ [Setting up your MediaConvert job for non\-linear watermarking](setting-up-non-linear-watermarking.md)
+ [How AWS Elemental MediaConvert interacts with your Nielsen SID/TIC server in the AWS Cloud](how-mediaconvert-interacts-with-your-nielsen-sid-tic-server-in-the-aws-cloud.md)