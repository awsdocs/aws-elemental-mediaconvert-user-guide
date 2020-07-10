# Modifying custom presets in MediaConvert<a name="modifying-presets"></a>

You can adjust the settings and field values in your custom presets\. You can't change system presets, but you can duplicate them and modify the duplicate, as described in [Creating a custom preset from a system preset](create-custom-preset-from-system-preset.md)\.

After you modify a preset, jobs that use the preset will run with the new settings, including the following:
+ Jobs that directly specify the custom preset\.
+ Jobs that you create based on a template that uses the custom preset\.
+ Jobs that you duplicate from your job history that use the custom preset\. The original job used the settings in the preset as they were at the time; the new job uses the current settings\.

**To modify a custom output preset**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar of the MediaConvert console, choose the region where the preset was created\.

   System presets are available in all regions\. Custom presets appear only in the region where they are created\.  
![\[Choose a region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Output presets**\.

1. Choose the name of the custom preset that you want to modify\.

1. Adjust the settings\.

1. Choose **Save**\.