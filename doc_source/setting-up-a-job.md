# Setting Up a Job in AWS Elemental MediaConvert<a name="setting-up-a-job"></a>

An AWS Elemental MediaConvert job does the work of transcoding a media file into packages and files in various formats and in different sizes for distribution to end viewers\. When you create a job, you specify the information that the service requires to perform the transcoding: which file to transcode, which types of files to create and where to store them, which encoding settings to use, which advanced features to apply, and so on\.

To set up a job, you define input files for the service to transcode, and you specify the source for each video, audio, and captions media element\. That source might be a specific part of the primary input file, or it might be a separate file\. Next, you specify the types of output files and packages that you want AWS Elemental MediaConvert to generate from the input\. You also specify the detailed encoding settings to produce the quality and type of output that you want\. The following illustration shows these pieces of a job that you set up\.

![\[AWS Elemental MediaConvert jobs are made up of input, ABR streaming output groups, and standalone file output groups. Input selectors define the video, audio, and captions elements of the input. Outputs and output selectors define which of these elements are included in the files and packages that the job creates.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/Job_overview.png)

To set up your job, complete the procedures in the following topics\.

**Topics**
+ [Optional: Pause Your Queues](optional-pause-the-queue.md)
+ [Step 1: Specify Input Files](specify-input-settings.md)
+ [Step 2: Create Input Selectors](create-selectors.md)
+ [Step 3: Create Output Groups](specify-output-groups.md)
+ [Step 4: Create Outputs](create-outputs.md)
+ [Step 5: Specify Global Job Settings](specify-global-job-settings.md)
+ [Creating and Setting Up File Outputs](create-outputs-in-file-output-groups.md)
+ [Using Variables in Your Job Settings](using-variables-in-your-job-settings.md)