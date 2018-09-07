# Setting Up AWS Elemental MediaConvert Resources for Cost Allocation Through Tagging<a name="setting-up-resources-for-catt"></a>

You can use the AWS Billing and Cost Management dashboard to set up a monthly cost allocation report that shows what AWS charges you for transcoding, sorted by resource\. You can set up your jobs so that your job outputs are sorted by tags on the queue, job template, or output preset\. That is, you can sort your bill by the tags you put on the queue you submit the job to, the the job template you create the job from, or the output presets you use to set up the individual outputs of the job\.

**To set up cost allocation through tagging for your AWS Elemental MediaConvert charges**

1. Tag the queues, job templates, or output presets that you intend to sort your bill by\. For instructions, see the other topics in this chapter\.

1. Create your transcoding jobs, specifying how you want your costs allocated as follows:

   1. On the **Create job** page, in the **Job** pane on the left, under **Job settings**, choose **Settings**\.

   1. In the **Job settings** section on the right, for **Billing tag source**, choose whether to sort the job's outputs by the tags on the queue, job template, or output presets that you use to create the job\.

1. Activate these tags on the AWS Billing and Cost Management dashboard\. For more information, see [Activating User\-Defined Cost Allocation Tags](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/activating-tags.html) in the *Billing and Cost Management User Guide*\.

1. Set up your report\. For more information, see [Monthly Cost Allocation Report](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/configurecostallocreport.html) in the *Billing and Cost Management User Guide*\.