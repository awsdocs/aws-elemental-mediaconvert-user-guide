# Gathering required captions information<a name="gather-required-captions-information"></a>

Before you set up captions in your job, note the following information:
+ The *input captions format*\. You must have this information ahead of time; MediaConvert does not read this from your input files\.
+ The *tracks* from the input captions that you intend to use in any of your outputs\.
+ The *output packages and files* that you intend to create with the job\. For information about specifying the output package or file type, see [Structuring complex jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\.
+ The *output captions format* that you intend to use in each output\.

  For supported output captions based on your input container, input captions format, and output container, see [Captions support tables by output container type](captions-support-tables-by-container-type.md)\. 
+ The *output captions tracks* that you intend to include for each output\. If you pass through teletext\-to\-teletext, all tracks in the input are available in the output\. Otherwise, the tracks that you include in an output might be a subset of the tracks that are available in the input\.