# Using output presets to specify the outputs of your AWS Elemental MediaConvert job<a name="using-a-preset-to-specify-a-job-output"></a>

When you specify the outputs of your MediaConvert job, you can use an output preset instead of choosing each output setting separately\.

**To specify a job output using an output preset**

1. Create a job in the usual way, as described in [Step 6: Create a job](create-a-job.md)\.

1. Create output groups as described in [Step 3: Create output groups](specify-output-groups.md)\.
**Tip**  
Many jobs have one output for each type of device that will play the video created by the job\.

1. On the **Create job** page, in the **Job** pane on the left, choose an output\. Outputs are listed in the **Output groups** section, under their output group\.

1. In the **Output settings** pane, choose an output preset from the **Preset** dropdown list\. For more information about individual settings, choose the **Info** link next to each setting\.
**Note**  
The **Preset** dropdown list shows only the presets that work with the type of output group that the output is in\.

1. For **Name modifier**, type a set of characters that will distinguish the files created from this output\. For example, you might use **\-DASH\-lo\-res** for the output in your DASH output group that has the lowest resolution\.

1. Repeat these steps for each output in your job that you want to specify with a preset\.

1. Finish creating the job as described in [Step 6: Create a job](create-a-job.md)\.