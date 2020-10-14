# Settings for scan type conversion<a name="settings-for-scan-type-conversion"></a>

To convert between interlaced to progressive video, specify the MediaConvert settings covered in this topic\. This topic offers conceptual information and guidance for choosing values for the MediaConvert settings related to interlacing and deinterlacing\. For directions for specifying them, see the procedures in the topic [Converting scan type](converting-scan-type.md)\.

Valid values for some of these settings depend on what you choose for the other settings\. For a table that shows how to specify them together correctly,  see [Valid settings combinations](valid-settings-combinations.md)\.

**Deinterlacer** preprocessor `(Deinterlacer`\)  
Use this parent setting to enable and disable deinterlacing\. If you simply enable the deinterlacer without specifying any further deinterlacing settings, your job will convert interlaced content to progressive\. For the default deinterlacing to work correctly, your input video must be interlaced and the frames of your input video must not have metadata that tagsthem as progressive\.

**Deinterlace Control** \(`DeinterlacerControl`\)  
This setting is a child of the deinterlacer setting\. You can optionally use **Deinterlace control** to have MediaConvert deinterlace all frames of your input video, including those that are tagged as progressive\. Only use this setting when you know that this metadata in your input video is wrong\.

**Deinterlace algorithm** \(`DeinterlaceAlgorithm)`  
This setting is a child of the deinterlacer setting\. You can optionally use **Deinterlace algorithm** to specify the way that MediaConvert does the deinterlacing to get the best quality for your content\. For sharper pictures, choose one of the motion adaptive interpolation options \(**Interpolate** or **Interpolate ticker**\)\. For smoother motion, choose one of the blend options \(**Blend** or **Blend ticker**\)\. When your source file includes moving text, such as a scrolling headline at the bottom of the frame, choose the ticker version of the algorithm\.

**Deinterlace mode** \(`DeinterlacerMode`\)  
This setting is a child of the deinterlacer setting\. You can optionally use **Deinterlace mode** to modify how MediaConvert applies deinterlacing\.  
Keep the default value, **Deinterlace**, to do regular deinterlacing\.  
Choose **Inverse telecine** to convert hard telecine \(29\.97 fps, interlaced\) to progressive video at 23\.976 fps\. Note that, when you use inverse telecine, you must still specify your output frame rate as 23\.97\. MediaConvert doesn't automatically set this\.   
Choose **Adaptive** to have MediaConvert automatically detect interlaced inputs and apply deinterlacing and inverse telecine to them\. Adaptive deinterlace mode is useful when you use output presets, job templates, or custom programming to apply the same job settings to transcode an entire library of assets\.  
When you choose **Adaptive** for this setting, MediaConvert automatically uses inverse telecine as well\.

**Interlace mode** \(`interlaceMode`\)  
When you create interlaced video, from either progressive or interlaced inputs, use this MediaConvert setting\. The default value of this setting is **Progressive**, so you can ignore this setting unless you want an interlaced output\.   
When you use an interlaced input and you keep the default setting, **Progressive**, for **Interlace mode**, you should also enable **Deinterlace**\. Otherwise, your progressive output will have very poor video quality\.
When you create interlaced outputs, use **Interlace mode** to specify the [field polarity](scan-type-vocabulary.md) of your outputs\. You can either directly specify the field that comes first, or you can set it to follow the polarity of the source input\. For jobs that have multiple inputs, the output might have a mix of top and bottom field first, depending on the polarity of the inputs\.  
When you set **Interlace mode** to follow the source and your input is progressive, the output's field polarity depends on which of the follow options you set\. **Follow, top field** results in an output that's top field first\. **Follow, bottom field** results in an output that's bottom field first\.

**Scan type** \(`inputScanType`\)  
Use this setting only when your input is progressive segmented frame \(PsF\)\. MediaConvert automatically detects progressive and interlaced inputs\. But it doesn't detect PsF\. When your input is PsF, set **Scan type** to **PsF** for better preservation of quality when you do deinterlacing and frame rate conversion\.