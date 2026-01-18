---
title: "Get-VBOAmazonS3CompatibleAccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboamazons3compatibleaccount.html"
last_updated: "12/23/2025"
product_version: "8.3.0.2201"
---

# Get-VBOAmazonS3CompatibleAccount


Short Description

Returns S3 Compatible storage account credentials.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get S3 Compatible storage account credentials by the Amazon S3 access key.

|  |
| --- |
| Get-VBOAmazonS3CompatibleAccount [-AccessKey <String>] [<CommonParameters>] |

* Get S3 Compatible storage account credentials by the Amazon S3 ID.

|  |
| --- |
| Get-VBOAmazonS3CompatibleAccount -Id <Guid> [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of account credentials that are managed by Veeam Backup for Microsoft 365 for the following types of object storage repositories:

* S3 Compatible object storage repository.
* IBM Cloud Object Storage.
* Wasabi Cloud Object Storage.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| AccessKey | Specifies an array of access keys for S3 Compatible storage account credentials. The cmdlet will return S3 Compatible storage account credentials with these access keys. | String | False | Named | False |
| Id | Specifies an array of IDs for S3 Compatible storage account credentials. The cmdlet will return S3 Compatible storage account credentials with these IDs. | Guid | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAmazonS3CompatibleAccount](vboamazons3compatibleaccount.md) object that contains S3 Compatible storage account credentials.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting S3 Compatible Storage Account Credentials by ID

|  |  |
| --- | --- |
| This command returns S3 Compatible storage account credentials by the S3 Compatible ID.  |  | | --- | | Get-VBOAmazonS3CompatibleAccount -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608 | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting S3 Compatible Storage Account Credentials by Access Key

|  |  |
| --- | --- |
| This command returns S3 Compatible storage account credentials by the specified access key.  |  | | --- | | Get-VBOAmazonS3CompatibleAccount -AccessKey "?Iqws8NewidZydk" | |


