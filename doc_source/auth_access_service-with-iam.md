# Understanding how AWS Elemental MediaConvert works with IAM<a name="auth_access_service-with-iam"></a>

AWS services can work with IAM in several ways\. AWS Elemental MediaConvert supports the following ways:
+ **Actions** – AWS Elemental MediaConvert supports using actions in a policy\. This allows an administrator to control whether an entity can complete an operation in MediaConvert\. For example, to allow an entity to update a job template by performing the `UpdateJobTemplate` AWS API operation, an administrator must attach a policy that allows the `iam:UpdateJobTemplate` action\. 
+ **Resource\-level permissions** – AWS Elemental MediaConvert supports resource\-level permissions\. Resource\-level permissions allow you to specify individual resources in the policy\. For example, you can grant permissions for a user to submit jobs only to a particular queue, or to use only job templates that have a particular ID in their name\.

  For an example IAM policy that grants resource\-level permissions, see [Example policy: Resource\-level access control](example-policies.md#example-policy-resource-level-access-control)\.

  For more information about limiting access at the resource level, see [Controlling access to resources](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_controlling.html#access_controlling-resources) in the *IAM User Guide*\.
+ **Authorization based on tags** – AWS Elemental MediaConvert supports authorization based on tags\. This feature allows you to use [resource tags](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/tag-editor.html) in the condition of a policy\. 

  For example, you might create a policy that allows the user access to all actions on all MediaConvert resources in the account, unless the resource or resources are tagged with the tag key `access` and either the value of `denied` or beginning with the string `deny`\. You do this by using the condition key `aws:RequestTag/<tag-key>`\. 

  For an example IAM policy that grants these permissions, see [Example policy: Tag\-based access control using resource tags](example-policies.md#example-policy-tag-based-access-control-using-resource-tags)\.

  For information about putting tags on your AWS Elemental MediaConvert resources, see [Tagging AWS Elemental MediaConvert resources](tagging-mediaconvert-resources.md)\.

  For more information about using tags to restrict access to your resources, see [Controlling access using tags](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_tags.html) in the *IAM User Guide*\.
+ **Temporary credentials** – AWS Elemental MediaConvert supports temporary credentials\. This feature allows you to sign in with federation, assume an IAM role, or assume a cross\-account role\. You obtain temporary security credentials by calling AWS STS API operations such as [AssumeRole](https://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRole.html) or [GetFederationToken](https://docs.aws.amazon.com/STS/latest/APIReference/API_GetFederationToken.html)\. 
+ **Service roles** – AWS Elemental MediaConvert supports service roles\. This feature allows a service to assume a [service role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html#iam-term-service-role) on your behalf\. This role allows the service to access resources in other services to complete an action on your behalf\. Service roles appear in your IAM account and are owned by the account\. This means that an IAM administrator can change the permissions for this role\. However, this might break the functionality of the service\. For information about creating this role, see [Step 3: Set up IAM permissions ](iam-role.md) in the *Getting Started* chapter of this guide\.

AWS Elemental MediaConvert doesn't support the following ways of interacting with IAM:
+ **Resource\-based policies** – AWS Elemental MediaConvert does not support resource\-based policies\. Resource\-based policies allow you to attach a policy to a resource within the service\. Resource\-based policies include a `Principal` element to specify which IAM identities can access that resource\. 
+ **Service\-linked roles** – AWS Elemental MediaConvert does not support service\-linked roles\. This feature allows a service to assume a [service\-linked role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html#iam-term-service-linked-role) on your behalf\. This role allows the service to access resources in other services to complete an action on your behalf\. Service\-linked roles appear in your IAM account, and are owned by the service\. An IAM administrator can view, but not edit the permissions for service\-linked roles\.

## AWS Elemental MediaConvert resources and operations<a name="mediaconvert-resources-and-operations"></a>

In AWS Elemental MediaConvert, the primary resource is *a job*\. In a policy, you use an Amazon Resource Name \(ARN\) to identify the resource that the policy applies to\.

The resources in the following table have unique ARNs associated with them\. 


****  

| Name in MediaConvert console | ARN format | 
| --- | --- | 
| [Job]( https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html) | arn:partition:mediaconvert:region:account:jobs/JobId | 
| [Queue]( https://docs.aws.amazon.com/mediaconvert/latest/apireference/queues.html) | arn:partition:mediaconvert:region:account:queues/QueueName | 
| [Output preset]( https://docs.aws.amazon.com/mediaconvert/latest/apireference/presets.html) | arn:partition:mediaconvert:region:account:presets/PresetName | 
| [Job template]( https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobtemplates.html) | arn:partition:mediaconvert:region:account:jobTemplates/JobTemplateName | 

AWS Elemental MediaConvert provides a set of operations to work with MediaConvert resources\. For a list of available operations for each resource, follow the links to the *AWS Elemental MediaConvert API Reference* in the preceding table\.

To allow or deny access to a subset of AWS Elemental MediaConvert resources, include the ARN of the resource in the `Resource` element of your policy\. The ARNs for MediaConvert have the following format:

```
arn:partition:mediaconvert:account:resource/ID
```

Replace the *partition*, *account*, *resource*, and *ID* variables with valid values\. Valid values can be the following:
+ *partition*: The partition for your AWS Region\. For most Regions, the partition is "aws\."
+ *account*: The ID of your AWS account\. This must be the same account that you used to create the IAM user to sign on to AWS Elemental MediaConvert\.
+ *resource*: The type of AWS Elemental MediaConvert resource\. 
+ *ID*: The ID of the AWS Elemental MediaConvert resource\.

For any of these variables, you can optionally use a wildcard \(`*`\) to indicate all resources of the specified type\. For example, the following ARN specifies all output presets for the account `111122223333`:

```
arn:aws:mediaconvert::111122223333:presets/*
```