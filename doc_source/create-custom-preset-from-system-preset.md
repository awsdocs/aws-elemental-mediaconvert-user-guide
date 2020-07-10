# Creating a custom preset based on a system preset in MediaConvert<a name="create-custom-preset-from-system-preset"></a>

MediaConvert doesn't allow you to modify system presets\. If you want a preset that is like a system preset but slightly modified, you can duplicate the system preset, customize the settings, and save it as a custom preset\.

**To create a custom output preset based on a system preset**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar of the MediaConvert console, choose the region where you want to create the new preset\.

   System presets are available in all regions\. Custom presets appear only in the region where you created them\.  
![\[Choose a region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Output presets**\.

1. In the **Output presets** pane, from the **Presets** dropdown list, choose **System presets**\.

1. Choose the name of the system preset that is most like the custom preset that you want to create\.

1. On the **Preset details** page, choose **Duplicate**\.

1. On the **Create preset** page, specify a name for the new preset\. Optionally, modify the description and category\.

   These values help you find the custom preset later if you [list your presets](listing-presets.md) and use the search function on the **Output presets** pane\.

1. Modify any output settings\.

   For more information about each setting, choose the **Info** link that is located next to the setting or next to the heading for the group of settings\.

1. Choose the **Create** button at the bottom of the page\.
**Note**  
This button looks like the **Create** button for creating a job, but in this context, choosing it creates the custom preset\.