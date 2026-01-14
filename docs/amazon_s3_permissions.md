---
title: "amazon_s3_permissions"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/amazon_s3_permissions.html"
last_updated: "1/16/2025"
product_version: "8.3.0.2201"
---


In this article

This section contains permissions required by Veeam Backup for Microsoft 365 for Amazon S3 object storage repository in the following usage scenarios:

* Data backup

Veeam Backup for Microsoft 365 supports Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes as a target for backup jobs.

* Backup copy

Veeam Backup for Microsoft 365 supports the following storage classes as a target for backup copy jobs:

* Amazon S3 Standard
* Amazon S3 Standard-Infrequent Access
* Amazon S3 One Zone-Infrequent Access
* Amazon S3 Glacier Instant Retrieval
* Amazon S3 Glacier Flexible Retrieval
* Amazon S3 Glacier Deep Archive

For more information about supported Amazon S3 storage classes, see [Supported Amazon S3 Storage Classes](supported_storage_classes_amazon.md).

|  |
| --- |
| Note |
| Make sure the account you are using has access to Amazon S3 buckets and folders. |

For each Amazon S3 object storage repository that Veeam Backup for Microsoft 365 uses regardless of the usage scenario, the following permissions must be granted:

* For EC2 instance (Amazon archiver appliance)

|  |
| --- |
| [  "ec2:StartInstances",  "ec2:RunInstances",  "ec2:StopInstances",  "ec2:TerminateInstances",  "ec2:CreateKeyPair",  "ec2:DeleteKeyPair",  "ec2:DescribeVpcs",  "ec2:CreateVpc",  "ec2:DeleteVpc",  "ec2:DescribeSubnets",  "ec2:CreateSubnet",  "ec2:DeleteSubnet",  "ec2:DescribeRouteTables",  "ec2:CreateRouteTable",  "ec2:DeleteRouteTable",  "ec2:CreateRoute",  "ec2:DeleteRoute",  "ec2:DescribeInternetGateways",  "ec2:CreateInternetGateway",  "ec2:AttachInternetGateway",  "ec2:DeleteInternetGateway",  "ec2:DescribeSecurityGroups",  "ec2:CreateSecurityGroup",  "ec2:DeleteSecurityGroup",  "ec2:DescribeConversionTasks",  "ec2:DescribeInstanceTypes",  "ec2:AuthorizeSecurityGroupIngress",  "ssm:GetParameter" ] |

* For Amazon S3 object storage repository

|  |
| --- |
| [  "s3:ListAllMyBuckets",  "s3:GetBucketLocation"  ] |

* For a bucket

|  |
| --- |
| [  "s3:ListBucket",  "s3:ListBucketMultipartUploads",  "s3:GetBucketObjectLockConfiguration",  "s3:GetBucketVersioning",  "s3:ListBucketVersions" ] |

* For an object

|  |
| --- |
| [  "s3:PutObject",  "s3:GetObject",  "s3:DeleteObject",  "s3:AbortMultipartUpload",  "s3:ListMultipartUploadParts",  "s3:RestoreObject",  "s3:GetObjectVersion",  "s3:GetObjectRetention",  "s3:PutObjectRetention",  "s3:DeleteObjectVersion" ] |

IAM Policy Example

The following is the example of an IAM policy:

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Sid": "S3Repository",             "Effect": "Allow",             "Action": [                 "s3:ListAllMyBuckets",                 "s3:GetBucketLocation",                 "s3:ListBucket",                 "s3:ListBucketMultipartUploads",                 "s3:GetBucketObjectLockConfiguration",                 "s3:GetBucketVersioning",                 "s3:ListBucketVersions",                 "s3:PutObject",                 "s3:GetObject",                 "s3:DeleteObject",                 "s3:AbortMultipartUpload",                 "s3:ListMultipartUploadParts",                 "s3:RestoreObject",                 "s3:GetObjectVersion",                 "s3:GetObjectRetention",                 "s3:PutObjectRetention",                 "s3:DeleteObjectVersion"             ],             "Resource": "arn:aws:s3:::\*"         },         {             "Sid": "EC2ArchiverAppliance",             "Effect": "Allow",             "Action": [                 "ec2:CreateTags",                 "ec2:DescribeInstances",                 "ec2:StartInstances",                 "ec2:RunInstances",                 "ec2:StopInstances",                 "ec2:TerminateInstances",                 "ec2:CreateKeyPair",                 "ec2:DeleteKeyPair",                 "ec2:DescribeVpcs",                 "ec2:CreateVpc",                 "ec2:DeleteVpc",                 "ec2:DescribeSubnets",                 "ec2:CreateSubnet",                 "ec2:DeleteSubnet",                 "ec2:DescribeRouteTables",                 "ec2:CreateRouteTable",                 "ec2:DeleteRouteTable",                 "ec2:CreateRoute",                 "ec2:DeleteRoute",                 "ec2:DescribeInternetGateways",                 "ec2:CreateInternetGateway",                 "ec2:AttachInternetGateway",                 "ec2:DeleteInternetGateway",                 "ec2:DescribeSecurityGroups",                 "ec2:CreateSecurityGroup",                 "ec2:DeleteSecurityGroup",                 "ec2:DescribeConversionTasks",                 "ec2:DescribeInstanceTypes",                 "ec2:AuthorizeSecurityGroupIngress",                 "ssm:GetParameter"             ],             "Resource": "\*"         }     ]  } |

For more information on how to create an IAM policy, see [this Amazon article](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html). For more information on permissions, see [this Amazon article](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-with-s3-actions.html).

Related Topics

[Supported Amazon S3 Storage Classes](supported_storage_classes_amazon.md)

Page updated 1/16/2025

Page content applies to build 8.3.0.2201
