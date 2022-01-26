# How to allow or disallow input location types using a policy<a name="input-policies"></a>

AWS Elemental MediaConvert supports Amazon S3, HTTPS, and HTTP input locations for your input media and files\. You can allow or disallow access to one or more of these input locations by using a MediaConvert policy\. 

By default, each Region in your AWS account does not have a policy and MediaConvert allows all supported input locations\. 

You only need to create a policy if you want to disallow access to one or more of these input locations\. Note that policies apply to individual Regions within your AWS account\.

**Create or change a policy**

To create or change a policy, submit a put\-policy command using the API, SDK, or CLI and include the policy in JSON\. Visit the [MediaConvert API Reference](https://docs.aws.amazon.com/mediaconvert/latest/apireference/policy.html) to learn more about supported policy commands and expected response codes\.

The following is an example of how to submit a policy using the CLI\. This example allows jobs with Amazon S3 and HTTPS inputs, and disallows jobs with HTTP inputs\. Run the following after filling in your specific endpoint URL:

```
aws mediaconvert --endpoint https://abc123def.mediaconvert.us-west-2.amazonaws.com put-policy --policy '{"S3Inputs":"ALLOWED", "HttpsInputs":"ALLOWED", "HttpInputs":"DISALLOWED"}'
```

If you don’t specify an input location in the policy JSON, MediaConvert will treat the input location as ALLOWED\. Here is another example that allows jobs with Amazon S3 and HTTPS inputs, and disallows jobs with HTTP inputs\. Run the following after filling in your specific endpoint URL:

```
aws mediaconvert --endpoint https://abc123def.mediaconvert.us-west-2.amazonaws.com put-policy --policy '{"HttpInputs":"DISALLOWED"}'
```

Note that the put\-policy command overwrites any existing policy in the Region\.

**Retrieve the current policy**

To retrieve the current policy in JSON, submit a get\-policy command\. For example, run the following after filling in your specific endpoint URL:

```
aws mediaconvert --endpoint https://abc123def.mediaconvert.us-west-2.amazonaws.com get-policy
```

**Delete the current policy**

To delete the current policy and allow all inputs \(reverting to the default behavior\), submit a delete\-policy command\. For example, run the following after filling in your specific endpoint URL:

```
aws mediaconvert --endpoint https://abc123def.mediaconvert.us-west-2.amazonaws.com delete-policy
```

**What happens when you try to submit a job with a disallowed input location?**

If you attempt to submit a job that specifies an input location that your policy disallows, MediaConvert will instead return an HTTP 400 \(BadRequestException\) error\. The error message will be: You specified an input location that your policy disallows\. Specify an allowed input location and resubmit your job\. Since MediaConvert prevents these jobs from being submitted, they will not appear in your job history\.

If you submit a job that specifies an input location that is allowed, but the job requires accessing another input location that is disallowed, your job will fail\. For example, you might encounter this if you specify an Apple HLS manifest on an allowed Amazon S3 location that references other input segment files on a disallowed HTTP location\. The job failure error code will be 3457 and the message will be: You specified an input location that your policy disallows\. Specify an allowed input location and resubmit your job\.