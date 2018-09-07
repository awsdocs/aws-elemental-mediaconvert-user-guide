# Gathering Required Captions Information<a name="gather-required-captions-information"></a>

Before you set up captions in your job, note the following information:
+ The *input captions format*\. You must have this information ahead of time; MediaConvert does not read this from your input files\.
+ The *languages* from the input captions that you intend to use in any of your outputs\.
+ The *output packages and files* that you intend to create with the job\. For information about specifying the output package or file type, see [Structuring Complex Jobs in MediaConvert](structuring-complex-jobs.md)\.
+ The *output captions format* that you intend to use in each output\.

  For supported output captions based on your input container, input captions format, and output container, see [Captions Support Tables by Output Container Type](captions-support-tables-by-container-type.md)\. 
+ The *output captions languages* that you intend to include for each output\. If you pass through teletext\-to\-teletext, all languages in the input are available in the output\. Otherwise, the languages that you include in an output might be a subset of the languages that are available in the input\.