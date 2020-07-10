# Using the QVBR rate control mode<a name="cbr-vbr-qvbr"></a>

The rate control mode that you choose for your output determines whether the encoder uses more data for complex parts of your video or maintains a constant amount of data per frame\. This chapter provides guidance for choosing the right rate control mode for your asset, depending on how you plan to distribute it\. In general, you get the best video quality for a given file size using quality\-defined variable bitrate \(QVBR\) for your rate control mode\.

## Comparison of QVBR with other rate control modes<a name="choosing-rate-control-mode"></a>

The rate control mode that you choose depends on the way that you will distribute your asset\. AWS Elemental MediaConvert offers the following choices for bit rate mode:

Quality\-Defined Variable Bitrate \(QVBR\) Mode  
Choose this mode for distribution over the internet \(OTT\) and for video on\-demand \(VOD\) download\. For best video quality for your file size, always choose this mode except in the following cases:  
+ You need your bit rate to be constant, for example, for distribution over fixed\-bandwidth networks
+ You need your total file size to not drop below the size that you specify, for example, to comply with contractual or regulatory requirements
When you choose QVBR, the encoder determines the right number of bits to use for each part of the video to maintain the video quality that you specify\. You can use the same QVBR settings for all your assets; the encoder automatically adjusts the file size to suit the complexity of the video\. For more information, see [Guidelines for using QVBR](#qvbr-guidelines)\.

Constant Bitrate \(CBR\) Mode  
Choose CBR only if you need the asset's bit rate to remain constant over time\. For example, you might need a constant bit rate if you distribute your assets over limited, fixed bandwidth networks\.  
When you choose CBR, the encoder caps the file size and quality with the value that you set for **Bitrate**\. The encoder uses the same number of bits for all parts of the video\.

Variable Bitrate Mode \(VBR\)   
Choose VBR if you distribute your asset over a network that allows for a changing bit rate, like the internet, but you need to specify the total file size of your asset\.   
With QVBR, if you set up your output for multi\-pass encoding, you can optionally specify a maximum average bit rate that caps the total file size of your output\. Only choose VBR if your file size can't be smaller than the size you specify\.
With VBR, you specify the asset's average bit rate; the encoder allocates bits so that more bits go to complex parts of the video\. The total file size \(excluding container, packaging, and audio data\) works out to the average bit rate that you specify \(in bits per second\) times the length of the asset \(in seconds\)\.  
When you use VBR, you get best results if you adjust your average bit rate to suit the complexity of each asset\.

The following graph illustrates how the varying bit rate modes \(QVBR and VBR\) save unnecessary bits and provide better quality compared to CBR\. The graph shows QVBR versus CBR, but the same principle applies to VBR\.

In the parts of the graph where the QVBR line is above the CBR line, as in the part labeled Area 1, the CBR capped bit rate limits video quality below that of other scenes, so QVBR gives you more consistent quality\. In the parts where the QVBR line drops below the CBR line, as in the part labeled Area 2, a low bit rate is sufficient for the same video quality, so QVBR saves bits and provides the opportunity for cost savings in storage and distribution through your content delivery network \(CDN\)\.

![\[This chart shows a comparison of bit rate over time for constant versus variable bit rate rate control modes. The line for CBR is nearly flat, because the bit rate barely changes over time. The line for VBR jumps far above it in places where the video is encoded with enough data to show good quality for complex video. The VBR line drops far below the CBR line in places where little data is needed for good quality.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/RateCtlModeChart.png)

## Guidelines for using quality\-defined variable bitrate mode<a name="qvbr-guidelines"></a>

When you use QVBR, you specify the quality level for your output and the maximum peak bit rate\. For reasonable values of those settings, the encoder chooses how many bits to use for each part of the video\. When you apply the same settings to several assets, your job outputs for simpler assets \(such as cartoons\) have smaller file sizes than your outputs for visually complex assets \(such as high\-motion sports with brightly dressed crowds in the background\)\.

This section provides information about the QVBR settings\. The following table provides a set of recommended values to get started with\. Specify your values for these settings when you create your outputs, as described in [Setting up a job](setting-up-a-job.md)\. For more information about each setting, choose a topic from the list that follows the table\.


| Resolution | Width | Height | QVBR quality level  | Max bit rate | 
| --- | --- | --- | --- | --- | 
| 1080p | 1920 | 1080 | 9 | 6000000 | 
| 720p | 1280 | 720 | 8 | 4000000 | 
| 720p | 1280 | 720 | 7 | 2000000 | 
| 480p | 640 | 480 | 7 | 1000000 | 
| 360p | 480 | 360 | 7 | 700000 | 
| 240p | 352 | 240 | 7 | 350000 | 

With all resolutions, don't specify a value for **Max average bitrate** unless you need to guarantee a total file size cap\. When you specify a maximum average bit rate, it reduces the benefit that QVBR provides in video quality to file size ratio\. To use **Max average bitrate**, you have to first set **Quality tuning level** to **Multi\-pass HQ**\. 

If you aren't using **Max average bitrate**, and you don't need multi\-pass encoding for other reasons, set **Quality tuning level** to **Single\-pass HQ**\. 

**Note**  
Multi\-pass encoding is a professional tier feature\. For more information about MediaConvert pricing tiers, see [MediaConvert pricing](https://aws.amazon.com/mediaconvert/pricing/)\.

### Setting QVBR quality tuning level<a name="qvbr-quality"></a>

You can specify the **QVBR quality level** on a scale between 1 and 10\. The encoder determines the right number of bits to use for each part of the video to maintain the video quality that you specify\. 

The best value for an output depends on how the output will be viewed\. In general, set **QVBR quality level** as shown in the following table\.


| Intended viewing device | Recommended QVBR quality level for 720p/1080p | 
| --- | --- | 
| Large\-screen TV | 8 or 9 | 
| PC or tablet | 7 | 
| Smartphone | 6 | 

The following graph shows how changing the quality level affects the bit rate that the encoder uses for different parts of the video\. While the lines for both level 7 and level 9 spike and drop in the same places, the encoder uses more bits total when the quality is set higher\.

![\[Both lines vary over time. The line that shows QVBR level 7 is shifted below the line for QVBR level 9.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/RateCtlModeChart2.png)