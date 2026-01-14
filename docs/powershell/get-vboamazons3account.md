---
title: "get-vboamazons3account"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboamazons3account.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns Amazon S3 storage account credentials.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get Amazon S3 storage account credentials by the Amazon S3 access key.

|  |
| --- |
| Get-VBOAmazonS3Account [-AccessKey <String>] [<CommonParameters>] |

* Get Amazon S3 storage account credentials by the Amazon S3 ID.

|  |
| --- |
| Get-VBOAmazonS3Account -Id <Guid> [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of existing Amazon S3 storage account credentials managed by Veeam Backup for Microsoft 365.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| AccessKey | Specifies an access key for Amazon S3 storage account credentials. The cmdlet will return Amazon S3 storage account credentials with this access key. | String | False | Named | False |
| Id | Specifies an array of IDs for Amazon S3 storage account credentials. The cmdlet will return Amazon S3 storage account credentials with these IDs. | Guid | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3Account object that contains Amazon S3 storage account credentials.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Amazon S3 Storage Account Credentials by ID

|  |  |
| --- | --- |
| This command returns Amazon S3 storage account credentials by the Amazon S3 ID.  |  | | --- | | Get-VBOAmazonS3Account -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608 | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Amazon S3 Storage Account Credentials by Access Key

|  |  |
| --- | --- |
| This command returns Amazon S3 storage account credentials by the specified access key.  |  | | --- | | Get-VBOAmazonS3Account -AccessKey "?Iqws8NewidZydk" | |

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
