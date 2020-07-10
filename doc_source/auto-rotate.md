# Using video rotation in AWS Elemental MediaConvert<a name="auto-rotate"></a>

For most inputs, you can choose how AWS Elemental MediaConvert rotates your video\. You can either specify the rotation or set the rotation to automatic\. Automatic rotation uses any rotation metadata contained in the input files\. Some cameras, often those in smartphones, record this rotation metadata when you turn the camera before you begin recording your video\. This rotation metadata, sometimes referred to as rotation atoms or boxes, provides rotation metadata to the player device that is used for viewing the video\. MediaConvert can automatically detect this rotation metadata and rotate your video during transcoding so that it appears correctly on all players\.

**Tip**  
If your video outputs are rotated in a way that you don't expect, a likely cause is that your input video has rotation metadata but your job settings don't specify that the service should use it\. Try setting **Rotate** to **Automatic**\. Find this setting on the **Create job** page, under **Input**, in the **Video selector** section\.

**Input file requirements**  
You can use rotation for inputs that have the following video characteristics:
+ Progressive video
+ Chroma subsampling scheme 4:2:2 or 4:2:0

**Topics**
+ [Specified rotation](manually-specified-rotation.md)
+ [Automatic rotation](automatic-rotation.md)