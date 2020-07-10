# What are policies?<a name="auth_access_what-are-policies"></a>

You control access in AWS by creating policies and attaching them to IAM identities or AWS resources\.

A policy is an object in AWS that, when associated with an entity or resource, defines their permissions\. AWS evaluates these policies when a principal, such as a user, makes a request\. Permissions in the policies determine whether the request is allowed or denied\. Most policies are stored in AWS as JSON documents\.

IAM policies define permissions for an action regardless of the method that you use to perform the operation\. For example, if a policy allows the [GetUser](https://docs.aws.amazon.com/IAM/latest/APIReference/API_GetUser.html) action, then a user with that policy can get user information from the AWS Management Console, the AWS CLI, or the AWS API\. When you create an IAM user, you can set up the user to allow console or programmatic access\. The IAM user can sign in to the console using a user name and password\. Or they can use access keys to work with the CLI or API\.

The following policy types, listed in order of frequency, can affect whether a request is authorized\. For more details, see [Policy types](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#access_policy-types) in the *IAM User Guide*\.
+ **Identity\-based policies** – You can attach managed and inline policies to IAM identities \(users, groups to which users belong, and roles\)\.
+ **Resource\-based policies** – You can attach inline policies to resources in some AWS services\. The most common examples of resource\-based policies are Amazon S3 bucket policies and IAM role trust policies\. AWS Elemental MediaConvert does not support resource\-based policies\. 
+ **Organizations SCPs** – You can use an AWS Organizations service control policy \(SCP\) to apply a permissions boundary to an AWS Organizations organization or organizational unit \(OU\)\. Those permissions are applied to all entities within the member accounts\.
+ **Access control lists \(ACLs\)** – You can use ACLs to control which principals can access a resource\. ACLs are similar to resource\-based policies, although they are the only policy type that does not use the JSON policy document structure\. AWS Elemental MediaConvert does not support ACLs\. 

These policies types can be categorized as *permissions policies* or *permissions boundaries*\.
+ **Permissions policies** – You can attach permissions policies to a resource in AWS to define the permissions for that object\. Within a single account, AWS evaluates all permissions policies together\. Permissions policies are the most common policies\. You can use the following policy types as permissions policies:
  + **Identity\-based policies** – When you attach a managed or inline policy to an IAM user, group, or role, the policy defines the permissions for that entity\.
  + **Resource\-based policies** – When you attach a JSON policy document to a resource, you define the permissions for that resource\. The service must support resource\-based policies\.
  + **Access control lists \(ACLs\)** – When you attach an ACL to a resource, you define a list of principals with permission to access that resource\. The resource must support ACLs\.
+ **Permissions boundaries** – You can use policies to define the permissions boundary for an entity \(user or role\)\. A permissions boundary controls the maximum permissions that an entity can have\. Permissions boundaries are an advanced AWS feature\. When more than one permissions boundary applies to a request, AWS evaluates each permissions boundary separately\. You can apply a permissions boundary in the following situations:
  + **Organizations** – You can use an AWS Organizations service control policy \(SCP\) to apply a permissions boundary to an AWS Organizations organization or organizational unit \(OU\)\.
  + **IAM users or roles** – You can use a managed policy for a user or role's permissions boundary\. For more information, see [Permissions boundaries for IAM entities](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html) in the *IAM User Guide*\.

**Topics**
+ [Identity\-based policies](#auth_access_manage-access-intro-identity-policies)
+ [Resource\-based policies](#auth_access_manage-access-intro-resource-policies)
+ [Policy access level classifications](#auth_access_policies-access-level)

## Identity\-based policies<a name="auth_access_manage-access-intro-identity-policies"></a>

You can attach policies to IAM identities\. For example, you can do the following:
+ **Attach a permissions policy to a user or a group in your account** – To grant a user permissions to create an AWS Elemental MediaConvert resource, such as a job, you can attach a permissions policy to a user or a group to which the user belongs\.
+ **Attach a permissions policy to a role \(grant cross\-account permissions\)** – You can attach an identity\-based permissions policy to an IAM role to grant cross\-account permissions\. For example, the administrator in account A can create a role to grant cross\-account permissions to another AWS account \(for example, account B\) or an AWS service as follows:

  1. Account A administrator creates an IAM role and attaches a permissions policy to the role that grants permissions on resources in account A\.

  1. Account A administrator attaches a trust policy to the role identifying account B as the principal who can assume the role\. 

  1. Account B administrator can then delegate permissions to assume the role to any users in account B\. Doing this allows users in account B to create or access resources in account A\. The principal in the trust policy can also be an AWS service principal if you want to grant an AWS service permissions to assume the role\.

  For more information about using IAM to delegate permissions, see [Access management](https://docs.aws.amazon.com/IAM/latest/UserGuide/access.html) in the *IAM User Guide*\.

For more information about users, groups, roles, and permissions, see [Identities \(users, groups, and roles\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html) in the *IAM User Guide*\. 

## Resource\-based policies<a name="auth_access_manage-access-intro-resource-policies"></a>

Resource\-based policies are JSON policy documents that you attach to a resource\. These policies allow you to specify what actions a specified principal can perform on that resource and under what conditions\. The most commonly known resource\-based policy is an Amazon S3 bucket\. Resource\-based policies are inline policies that exist only on the resource\. There are no managed resource\-based policies\.

Granting permissions to members of other AWS accounts using a resource\-based policy has some advantages over an IAM role\. For more information, see [How IAM roles differ from resource\-based policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_compare-resource-policies.html) in the *IAM User Guide*\.

AWS Elemental MediaConvert does not support resource\-based policies\.

## Policy access level classifications<a name="auth_access_policies-access-level"></a>

In the IAM console, actions are grouped using the following access level classifications:
+ **List** – Provide permission to list resources within the service to determine whether an object exists\. Actions with this level of access can list objects but cannot see the contents of a resource\. Most actions with the **List** access level can't be performed on a specific resource\. When you create a policy statement with these actions, you must specify **All resources** \(`"*"`\)\. 
+ **Read** – Provide permission to read but not edit the contents and attributes of resources in the service\. For example, the Amazon S3 actions `GetObject` and `GetBucketLocation` have the **Read** access level\.
+ **Write** – Provide permission to create, delete, or modify resources in the service\. For example, the Amazon S3 actions `CreateBucket`, `DeleteBucket` and `PutObject` have the **Write** access level\.
+ **Permissions management** – Provide permission to grant or modify resource permissions in the service\. For example, most IAM and AWS Organizations policy actions have the **Permissions management** access level\.
**Tip**  
To improve the security of your AWS account, restrict or regularly monitor policies that include the **Permissions management** access level classification\.
+ **Tagging** – Provide permission to create, delete, or modify tags that are attached to a resource in the service\. For example, the Amazon EC2 `CreateTags` and `DeleteTags` actions have the **Tagging** access level\.