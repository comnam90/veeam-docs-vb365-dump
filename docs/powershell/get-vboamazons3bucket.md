---
title: "get-vboamazons3bucket"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboamazons3bucket.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns Amazon S3 buckets.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get Amazon S3 buckets.

|  |
| --- |
| Get-VBOAmazonS3Bucket -AmazonS3ConnectionSettings <VBOAmazonS3ConnectionSettings> [-Name <String>] [-RegionId <String>] [<CommonParameters>] |

* Get S3 Compatible buckets.

|  |
| --- |
| Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings <VBOAmazonS3CompatibleConnectionSettings> [-Name <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns the VBOAmazonS3Bucket object that contains an array of Amazon buckets for the following Amazon services:

* Amazon S3
* S3 Compatible

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| AmazonS3ConnectionSettings | Specifies an active session with Amazon S3 object storage repository. The cmdlet will return an array of Amazon S3 buckets for this Amazon S3 object storage repository. | Accepts the VBOAmazonS3ConnectionSettings object.  To create this object, run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. | True | Named | False |
| Name | Specifies a name of the Amazon S3 bucket. The cmdlet will return the bucket with this name. | String | False | Named | False |
| RegionId | Specifies a region of Amazon S3 object storage repository.  For example, us-east-1.  For more information, see [this Amazon article](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.RegionsAndAvailabilityZones.html). | String | False | Named | False |
| AmazonS3CompatibleConnectionSettings | Specifies an active session with S3 Compatible object storage repository. The cmdlet will return an array of Amazon S3 buckets for this S3 Compatible object storage repository. | Accepts the VBOAmazonS3CompatibleConnectionSettings object.  To create this object, run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3Bucket object that contains an array of Amazon S3 buckets.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Amazon S3 Buckets

|  |  |
| --- | --- |
| This example shows how to get Amazon S3 buckets.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3ConnectionSettings -Account $account -RegionType Global  Get-VBOAmazonS3Bucket -AmazonS3ConnectionSettings $connection -RegionId eu-north-1 |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable.  1. Run the Get-VBOAmazonS3Bucket cmdlet. Set the $connection variable as the AmazonS3ConnectionSettings parameter value. Specify the RegionId parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting S3 Compatible Buckets

|  |  |
| --- | --- |
| This example shows how to get S3 Compatible buckets.  |  | | --- | | $account = Get-VBOAmazonS3CompatibleAccount -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000"  Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings $connection |  Perform the following steps:   1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. Specify the necessary parameters. Save the result to the $connection variable. 3. Run the Get-VBOAmazonS3Bucket cmdlet. Set the $connection variable as the AmazonS3CompatibleConnectionSettings parameter value. |

Related Commands

* [Get-VBOAmazonS3Account](get-vboamazons3account.md)
* [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md)
* [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md)
* [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
