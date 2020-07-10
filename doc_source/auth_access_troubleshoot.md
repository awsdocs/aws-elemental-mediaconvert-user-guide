# Troubleshooting authentication and access control<a name="auth_access_troubleshoot"></a>

Use the following information to help you diagnose and fix common issues that you might encounter when working with IAM\.

**Topics**
+ [I'm not authorized to perform an action in AWS Elemental MediaConvert](#auth_access_troubleshoot-no-permissions)
+ [I'm an administrator and want to allow others to access AWS Elemental MediaConvert](#auth_access_troubleshoot-admin-allow-access)
+ [I want to understand IAM without becoming an expert](#auth_access_troubleshoot-iam-expert)

## I'm not authorized to perform an action in AWS Elemental MediaConvert<a name="auth_access_troubleshoot-no-permissions"></a>

If you receive an error in the AWS Management Console that tells you that you're not authorized to perform an action, then you must contact the administrator that provided you with your user name and password\. 

The following example error occurs when an IAM user named `my-user-name` tries to use the console to perform the GetJob action, but does not have permissions:

```
User: arn:aws:iam::123456789012:user/my-user-name is not authorized to perform: MediaConvert:GetJob on resource: my-example-job-arn
```

For this error, ask your administrator to update your policies to allow you to access the `my-example-job-arn` resource using the `MediaConvert:GetJob` action\.

## I'm an administrator and want to allow others to access AWS Elemental MediaConvert<a name="auth_access_troubleshoot-admin-allow-access"></a>

To allow others to access AWS Elemental MediaConvert, you must create an IAM entity \(user or role\) for the person or application that needs access\. They will use the credentials for that entity to access AWS\. You must then attach a policy to the entity that grants them the correct permissions in MediaConvert\. 

## I want to understand IAM without becoming an expert<a name="auth_access_troubleshoot-iam-expert"></a>

To learn more about IAM terms, concepts, and procedures, see the following pages:
+ [What is authentication?](auth_access_what-is-authentication.md)
+ [What is access control?](auth_access_what-is-access-control.md)
+ [What are policies?](auth_access_what-are-policies.md)