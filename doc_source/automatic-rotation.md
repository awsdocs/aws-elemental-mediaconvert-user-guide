# Automatic rotation<a name="automatic-rotation"></a>

If your video has embedded rotation metadata, AWS Elemental MediaConvert can detect it and automatically rotate your video content so that it's oriented correctly in your outputs\.

**Note**  
AWS Elemental MediaConvert doesn't pass through rotation metadata\. Regardless of how you set **Rotate**, job outputs don't have rotation metadata\.

**Additional input file requirements for automatic rotation**  
In addition to the general input restrictions for the rotate feature, to use automatic rotation your input file must conform to these limitations:
+ Input container: \.mov or \.mp4
+ Rotation metadata specifying 90, 180, or 270\-degree rotation

  If your rotation metadata is within one degree less or more than the values listed here, the service will round to a supported value\.

**Note**  
If your input file has rotation metadata that specifies a rotation other than those listed here, the service defaults to no rotation\.

**To enable automatic rotation**

1. Check that your input container is \.mov or \.mp4 and that your input has rotation metadata\.

1. On the **Create job** page, in the **Job** pane on the left, in the **Inputs** section, choose the input that has rotation metadata\.

1. In the **Video selector** section on the left, for **Rotate**, choose **Automatic**\.

**Note**  
AWS Elemental MediaConvert doesn't rotate images and motion graphics that you overlay\. If you use the image inserter \(graphic overlay\) feature or the motion image inserter \(motion graphic overlay\) feature with the rotate feature, rotate your overlay before you upload it\. Specify the position of your overlays as you want them to appear on the video after rotation\.