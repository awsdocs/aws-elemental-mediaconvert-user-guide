# Step 3: Add the Amazon SNS topic and finish your rule<a name="add-target-and-finish-rule"></a>

Next, add the target \(the Amazon SNS topic\) that you created in step 1 to the CloudWatch Events rule that you started in step 2\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/CloudWatchEvents_tutorial-rule.png)

**To add the SNS topic and finish the CloudWatch Events rule**

1. In the **Targets** section, choose **Add targets**, and then change the default **Lambda function** to **SNS topic**\. 

1. For **Topic\***, choose **MediaConvertJobErrorAlert**\.

1. Choose the **Configure details** button\.

1. For **Rule definition**, enter a name and description for your rule, and then choose **Create rule**\.