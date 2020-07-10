# Example inline policy with kms:decrypt and kms:GenerateDataKey<a name="example-inline-policy-kms-decrypt-generatedatakey"></a>

This policy grants permissions for both kms:Decrypt and kms:GenerateDataKey\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "kms:Decrypt",
        "kms:GenerateDataKey"
      ],
      "Resource": "*",
      "Condition": {
        "StringLike":

{           "kms:ViaService": "s3.*amazonaws.com"         }
      }
    }
  ]
}
```