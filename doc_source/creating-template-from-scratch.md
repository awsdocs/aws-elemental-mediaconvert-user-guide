# Creating a custom job template in AWS Elemental MediaConvert<a name="creating-template-from-scratch"></a>

Job templates specify the settings that apply to all outputs of a transcoding job\. System job templates have settings that are specified for you; custom job templates have settings that are specified by you or by another user of your AWS account\. 

You can create a job template by individually specifying the settings for each output\. Or you can create a custom preset by specifying a preset for each output's settings, as described in [Using output presets](using-a-preset-to-specify-a-job-output.md)\.

**To create a custom job template**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar of the MediaConvert console, choose the region where you want to create the job template\.

   System job templates are available in all regions\. Custom job templates appear only in the region where you created them\.  
![\[Choose a region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Job templates**\.

1. In the **Job templates** pane, choose the **Create template** button\.

1. In the **General information** pane, specify at a minimum the name of the new job template\. Optionally, provide a description and a category\.

   These values help you find the custom preset later if you [list your job templates](listing-job-templates.md) and use the search function on the **Job templates** pane\.

1. In the **Job template** pane, add inputs, output groups, outputs, and job\-wide settings\. 

   The procedure for this is the same as described in [Setting up a job](setting-up-a-job.md), except that you don't specify the location and file name of your input, and you don't specify the IAM role that the service assumes so that it can access your resources\.
**Note**  
If you set up outputs by referring to output presets, make sure to specify input audio and captions selectors to correspond with any output audio and captions that are specified in the preset\. For example, if you use an output preset with three audio tracks that use audio selectors 1, 2, and 3, make sure that the input that you specify has audio selectors 1, 2, and 3\.