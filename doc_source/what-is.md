# What Is AWS Elemental MediaConvert?<a name="what-is"></a>

AWS Elemental MediaConvert is a file\-based video processing service that provides scalable video processing for content owners and distributors with media libraries of any size\. AWS Elemental MediaConvert offers advanced features that enable premium content experiences, including:

+ professional broadcast codecs that support increased bit depth and HDR content creation

+ still graphic overlays

+ advanced audio

+ digital rights management \(DRM\)

+ closed captioning support

AWS Elemental MediaConvert offers support for various input formats and adaptive bitrate \(ABR\) packaging output formats for delivering high\-quality content from a range of sources onto primary and multiscreen devices\.

For simple use cases, you can set up an AWS Elemental MediaConvert transcoding job in just a few steps\. For instructions, see [Getting Started with AWS Elemental MediaConvert](getting-started.md)\. 

 AWS Elemental MediaConvert has the following components:

Jobs  
A *job* does the work of transcoding\. Each job converts an input file into an output file or files\. Inputs and outputs can contain one or more of video, audio, and captions, either together or in separate files\. Before you begin creating jobs, make sure that you know what your input files are and what they contain\. Also make sure that you know what files you would like to create as output and what format you would like them in\.   
When you create a job, you specify the name of the file that you want to transcode, the names that you want AWS Elemental MediaConvert to give to the finished output files, and several other settings\.

Queues  
A *queue* allows you to manage the resources that are available to your account for parallel processing of jobs\. AWS Elemental MediaConvert processes jobs that are submitted to a queue in parallel until the resources that are available to the account are used\. If the account is already using all of its resources, AWS Elemental MediaConvert begins processing the next job in the queue after it finishes one of the jobs that it's currently processing\.   
All jobs must be submitted to a queue\. If you don't specify the queue when you create jobs, AWS Elemental MediaConvert sends them to a default queue and starts them in the order in which you create them\.   
If you have jobs of differing priorities, you can handle high\-priority jobs by creating a different queue from the default queue\. This distributes the resources that are available to the account across the two queues\. Because jobs across multiple queues are processed in parallel \(until the resources that are available to the account are used\), you can submit most jobs into the default queue and use the other queue only when you need to transcode a job immediately\. It is important to note that creating additional queues does not increase the resources that are available to the account\.   
The time that is required to complete a job varies significantly based on the size of the file that you're converting and the job specifications\. Accordingly, jobs don't necessarily complete in the order in which you create them\. You can temporarily stop processing jobs by pausing the queue\. AWS Elemental MediaConvert does not process jobs from a paused queue; however, you can still submit jobs to a paused queue\. You can also cancel jobs in a queue that have not yet started transcoding\. 

Presets  
 A *preset* is a saved group of encoding settings for a single output\. You can create many common outputs by simply selecting a system preset\. You can also create your own custom presets, either by duplicating and modifying an existing preset or by creating one from scratch\.  
When you create a job, you can specify a preset you want to use or you can individually specify your encoding settings\.

Job templates  
A *job template * specifies all the settings for a complete job, except for your IAM role and those settings that are likely to change for each job, such as the input file location and name, and user metadata you might tag the job with\. You create a job templates by specifying all input settings other than input location and filename and then specifying all the outputs the job will generate\. You can specify the settings for each output by choosing a preset for the output or by specifying each output setting individually\.