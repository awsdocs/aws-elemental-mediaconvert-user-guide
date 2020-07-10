# Using variables in your job settings<a name="using-variables-in-your-job-settings"></a>

You can use variables, also called *format identifiers*, in your job settings\. Format identifiers are values that you can put in your job settings that resolve differently in your outputs depending on the characteristics of the input files or the job\. They are particularly useful in output presets, job templates, and jobs that you intend to duplicate and re\-use\. 

For example, you might use the date format identifier `$d$` for your **Destination** setting\. If you want your outputs organized by the date and time that the job starts, for **Destination** you might enter **s3://mediaconvert\-output\-bucket/$d$/**\. For a job that starts June 4, 2020, the service will create your outputs in `s3://mediaconvert-output-bucket/20200604/`\.

For a list of the available format identifiers and examples of how to use them, see [List of settings variables with examples](list-of-settings-variables-with-examples.md)\.

For information about format identifiers that function differently in streaming outputs, see [Using settings variables with streaming outputs](using-settings-variables-with-streaming-outputs.md)\.

**Topics**
+ [List of settings variables with examples](list-of-settings-variables-with-examples.md)
+ [Using settings variables with streaming outputs](using-settings-variables-with-streaming-outputs.md)
+ [Specifying a minimum number of digits](specifying-a-minimum-number-of-digits.md)