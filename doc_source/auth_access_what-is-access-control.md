# What is access control?<a name="auth_access_what-is-access-control"></a>

After you sign in \(are authenticated\) to AWS, your access to AWS resources and operations is controlled using policies\. Access control is also known as authorization\.

During authorization, AWS uses values from the request context to check for policies that apply\. It then uses the policies to determine whether to allow or deny the request\. Most policies are stored in AWS as JSON documents and specify the permissions that are allowed or denied for principals\. For more information about the structure and contents of JSON policy documents, see [What are policies?](auth_access_what-are-policies.md)\.

Policies let an administrator specify who has access to AWS resources, and what actions they can perform on those resources\. Every IAM entity \(user or role\) starts with no permissions\. In other words, by default, users can do nothing, not even view their own access keys\. To give a user permission to do something, an administrator must attach a permissions policy to a user\. Or they can add the user to a group that has the intended permissions\. When an administrator then give permissions to a group, all users in that group get those permissions\.

You might have valid credentials to authenticate your requests, but unless an administrator grants you permissions you can't create or access AWS Elemental MediaConvert resources\. For example, you must have explicit permissions to create an AWS Elemental MediaConvert job\.

As an administrator, you can write a policy to control access to the following:
+ **[AWS for Principals](#auth_access_controlling-principals)** – Control what the  user, account, or service making the request \(the *principal*\) is allowed to do\. 
+ **[IAM Identities](#auth_access_controlling-identities)** – Control which IAM identities \(groups, users, and roles\) can be accessed and how\.
+ **[IAM Policies](#auth_access_controlling-policies)** – Control who can create, edit, and delete customer managed policies, and who can attach and detach all managed policies\.
+ **[AWS Resources](#auth_access_controlling-resources)** – Control who has access to resources using an identity\-based policy or a resource\-based policy\.
+ **[AWS Accounts](#auth_access_controlling-principal-accounts)** – Control whether a request is allowed only for members of a specific account\.

## Controlling access for principals<a name="auth_access_controlling-principals"></a>

Permissions policies control what you, as a principal, are allowed to do\. An administrator must attach an identity\-based permissions policy to the identity \(user, group, or role\) that provides your permissions\. Permissions policies allow or deny access to AWS\. Administrators can also set a permissions boundary for an IAM entity \(user or role\) to define the maximum permissions that the entity can have\. Permissions boundaries are an advanced IAM feature\. For more information about permissions boundaries, see [Permissions boundaries for IAM identities](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html) in the *IAM User Guide*\.

For more information and an example of how to control AWS access for principals, see [Controlling access for principals](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_controlling.html#access_controlling-principals) in the *IAM User Guide*\.

## Controlling access to identities<a name="auth_access_controlling-identities"></a>

Administrators can control what you can do to an IAM identity \(user, group, or role\) by creating a policy that limits what can be done to an identity, or who can access it\. Then attach that policy to the identity that provides your permissions\. 

For example, an administrator might allow you to reset the password for three specific users\. To do this, they attach a policy to your IAM user that allows you to reset the password for only yourself and users with the ARN of the three specified users\. This allows you to reset the password of your team members but not other IAM users\.

For more information and an example of using a policy to control AWS access to identities, see [Controlling access to identities](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_controlling.html#access_controlling-identities) in the *IAM User Guide*\.

## Controlling access to policies<a name="auth_access_controlling-policies"></a>

Administrators can control who can create, edit, and delete customer managed policies, and who can attach and detach all managed policies\. When you review a policy, you can view the policy summary that includes a summary of the access level for each service within that policy\. AWS categorizes each service action into one of four *access levels* based on what each action does: `List`, `Read`, `Write`, or `Permissions management`\. You can use these access levels to determine which actions to include in your policies\. For more information, see [Understanding access level summaries within policy summaries](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_understand-policy-summary-access-level-summaries.html) in the *IAM User Guide*\.

**Warning**  
You should restrict Permissions Management access\-level permissions in your account\. Otherwise, your account members can create policies for themselves with more permissions than they should have\. Or they can create separate users with full access to AWS\. 

For more information and an example of how to control AWS access to policies, see [Controlling access to policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_controlling.html#access_controlling-policies) in the *IAM User Guide*\.

## Controlling access to resources<a name="auth_access_controlling-resources"></a>

Administrators can control access to resources using an identity\-based policy or a resource\-based policy\. In an identity\-based policy, you attach the policy to an identity and specify what resources that identity can access\. In a resource\-based policy, you attach a policy to the resource that you want to control\. In the policy, you specify which principals can access that resource\.

**Note**  
AWS Elemental MediaConvert doesn't support resource\-based policies\.

For more information, see [Controlling access to resources](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_controlling.html#access_controlling-resources) in the *IAM User Guide*\.

### Resource creators do not automatically have permissions<a name="NoDefaultPermissions"></a>

All resources in an account are owned by the account, regardless of who created those resources\. The AWS account root user is the account owner, and therefore  has permission to perform any action on any resource in the account\.

**Important**  
We strongly recommend that you do not use the root user for your everyday tasks, even the administrative ones\. Instead, adhere to the [best practice of using the root user only to create your first IAM user](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#create-iam-users)\. Then securely lock away the root user credentials and use them to perform only a few account and service management tasks\. To view the tasks that require you to sign in as the root user, see [AWS tasks that require root user](https://docs.aws.amazon.com/general/latest/gr/aws_tasks-that-require-root.html)\.

Entities \(users or roles\) in your account must be granted access to create a resource\. But just because they create a resource does not mean they automatically have full access to that resource\. You must explicitly grant permissions for each action\. Additionally, you can revoke those permissions at any time, as long as you have access to manage user and role permissions\.

## Controlling access to principals in a different account<a name="auth_access_controlling-principal-accounts"></a>

Administrators can use AWS resource\-based policies, IAM cross\-account roles, or the AWS Organizations service to allow principals in another account to access resources in your account\.

For some AWS services, you can grant cross\-account access to your resources\. To do this, you attach a policy directly to the resource that you want to share, instead of using a role as a proxy\. If the service supports this policy type, then the resource that you want to share must also support resource\-based policies\. Unlike a user\-based policy, a resource\-based policy specifies who \(in the form of a list of AWS account ID numbers\) can access that resource\. AWS Elemental MediaConvert does not support resource\-based policies\.

Cross\-account access with a resource\-based policy has some advantages over a role\. With a resource that is accessed through a resource\-based policy, the principal \(person or application\) still works in the trusted account and does not have to give up their user permissions in place of the role permissions\. In other words, the principal has access to resources in the trusted account *and* in the trusting account at the same time\. This is useful for tasks such as copying information from one account to another\. For more information about using cross\-account roles, see [Providing access to an IAM user in another AWS account that you own](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_aws-accounts.html) in the *IAM User Guide*\.

AWS Organizations offers policy\-based management for multiple AWS accounts that you own\. With Organizations, you can create groups of accounts, automate account creation, and apply and manage policies for those groups\. Organizations enables you to centrally manage policies across multiple accounts, without requiring custom scripts and manual processes\. Using AWS Organizations, you can create service control policies \(SCPs\) that centrally control AWS service use across AWS accounts\. For more information, see [What is AWS Organizations?](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_introduction.html) in the *AWS Organizations User Guide*\.