# Creating a custom preset in MediaConvert<a name="creating-preset-from-scratch"></a>

Output presets specify the settings that apply to a single output of a transcoding job\. System presets have the output settings that are specified for you; custom presets have settings that are specified by you or by another user of your AWS account\. 

You can create a custom preset by individually specifying the settings, as described in this topic\. Or you can create a custom preset by duplicating and modifying an existing preset, as described in [Creating a custom preset from a system preset](create-custom-preset-from-system-preset.md)\.

**To create a custom output preset**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar of the MediaConvert console, choose the region where you want to create the preset\.

   System presets are available in all regions\. Custom presets appear only in the region where they are created\.  
![\[Choose a region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Output presets**\.

1. In the **Output presets** pane, choose the **Create preset** button\.

1. In the **Preset settings** pane, specify at a minimum the name of the new preset\. Optionally, provide a description and a category\.

   These values help you find the custom preset later if you [list your presets](listing-presets.md) and use the search function on the **Output presets** pane\.

1. In the **Preset settings** pane, choose the container for the output\.
**Tip**  
It's important to specify a container that is appropriate to the output type that you intend to create with the preset\. When you choose a system or custom preset as part of creating a job, the console displays only the presets that specify a container that is valid for the output group\.

1. Choose your output settings\.

   For more information about each setting, choose the **Info** link located next to the setting or next to the heading for the group of settings\.

1. Choose the **Create** button at the bottom of the page\.