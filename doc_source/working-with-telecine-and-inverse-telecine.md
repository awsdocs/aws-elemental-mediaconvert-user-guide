# Working with telecine in AWS Elemental MediaConvert<a name="working-with-telecine-and-inverse-telecine"></a>

**Tip**  
If your video processing workflow doesn't require telecine, choose a standard progressive output\.

When you convert the frame rate from 23\.976 frames per second \(fps\) to 29\.97 fps, and your output scan type is interlaced, you can optionally use the **Telecine** setting to enable hard or soft telecine\. *Hard telecine* produces a 29\.97i output by duplicating interlaced video frame fields onto multiple frames\. *Soft telecine* produces a 23\.976 fps output that signals to the video player device to do the conversion during play back\. Generally, broadcasters use telecine when preparing film assets for broadcasting to NTSC set\-top boxes\.

How you set some of the related MediaConvert settings depends on the scan type and frame rate of your input, and whether your input has telecine frames already\. Details about related settings are in the following list\. For a summary table, see [Valid settings combinations](valid-settings-combinations.md)\.Related settings

**Frame rate** \(`framerateControl`, `framerateNumerator`, `framerateDenominator`\)  
When you enable the telecine setting, you must still specify your output frame rate as 29\.97\. MediaConvert doesn't automatically set this\.

**Frame rate conversion algorithm** \(`framerateConversionAlgorithm`\)  
When your input frame rate isn't 23\.976 and you enable **Telecine**, MediaConvert uses the frame rate conversion algorithm that you specify to convert your frame rate to 23\.976 before applying telecine\. When your input frame rate is 23\.976, MediaConvert ignores any value you set for **Frame rate conversion algorithm**\.

**Deinterlacer** preprocessor `(Deinterlacer`\)  
Enable the deinterlacer when you want to remove interlacing to create a progressive output\. When you remove interlacing from a telecine input, make sure to also set **Deinterlace mode** to **Inverse telecine**\.  
For more information about deinterlacing, see [Working with progressive and interlaced scan types](working-with-scan-type.md)\.

**Interlace mode** \(`interlaceMode`\)  
When your input is progressive and you set up a telecine output, apply interlacing using **Interlace mode**\.  
For more information about interlacing, see [Working with progressive and interlaced scan types](working-with-scan-type.md)\.

**Scan type** \(`inputScanType`\)  
Use this setting only when your input is progressive segmented frame \(PsF\)\. MediaConvert automatically detects progressive and interlaced inputs\. But it doesn't detect PsF\. When your input is PsF, set **Scan type** to **PsF** for better preservation of quality when you do deinterlacing and frame rate conversion\.

For console and API procedures for setting up a job to convert a video to or from telecine, see [Converting scan type](converting-scan-type.md)\.