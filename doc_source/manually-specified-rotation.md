# Specified rotation<a name="manually-specified-rotation"></a>

When you specify the rotation for your input, AWS Elemental MediaConvert rotates the video from your input clockwise the amount that you specify\. This rotation applies to all outputs in the job\. You can rotate clockwise by 90, 180, or 270 degrees\. The following image shows a video output from a job that specifies a 90\-degree rotation\.

**Note**  
AWS Elemental MediaConvert doesn't pass through rotation metadata\. Regardless of how you set **Rotate**, job outputs don't have rotation metadata\.

![\[The video is rotated so that the top of the pre-rotation image is parallel to the right edge of the post-rotation video frame. Black vertical bars on the right and left accommodate the difference between the aspect ratio of the original video and the rotated video.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/auto-rotate-example.jpg)

**To specify the rotation of your video**

1. On the **Create job** page, in the **Job** pane on the left, in the **Inputs** section, choose the input that you want to rotate\.

1. In the **Video selector** section on the left, for **Rotate**, choose the amount of clockwise rotation that you want\.

If you use the API or an SDK, you can find this setting in the JSON file of your job\. The setting name is `rotate`\. Find the [rotate](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-videoselector-rotate) property in the AWS Elemental MediaConvert API Reference\.

**Note**  
AWS Elemental MediaConvert doesn't rotate images and motion graphics that you overlay\. If you use the image inserter \(graphic overlay\) feature or the motion image inserter \(motion graphic overlay\) feature with the rotate feature, rotate your overlay before you upload it\. Specify the position of your overlays as you want them to appear on the video after rotation\.