---
title: "get-vboamazons3folder"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboamazons3folder.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns Amazon S3 folders.

Syntax

|  |
| --- |
| Get-VBOAmazonS3Folder -Bucket <VBOAmazonS3Bucket> [-Name <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns the VBOAmazonS3Folder object that contains an array of Amazon S3 folders. You can get the array of the folders for the following types of Amazon S3 object storage repositories:

* Amazon S3

* S3 Compatible

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Bucket | Specifies an Amazon S3 bucket. The cmdlet will return an array of the folders added to this bucket. | Accepts the VBOAmazonS3Bucket object.  To get this object, run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. | True | Named | False |
| Name | Specifies a name of the Amazon S3 folder. The cmdlet will return the folder with this name. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3Folder object that contains an array of Amazon S3 folders.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Amazon S3 Folders

|  |  |
| --- | --- |
| This example shows how to get Amazon S3 folders.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3ConnectionSettings -Account $account -RegionType Global  $bucket = Get-VBOAmazonS3Bucket -AmazonS3ConnectionSettings $connection -RegionId eu-north-1  Get-VBOAmazonS3Folder -Bucket $bucket -Name "Reports 09" |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the necessary parameters. Save the result to the $connection variable.  1. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Set the $connection variable as the AmazonS3ConnectionSettings parameter value. Specify the RegionId parameter value. Save the result to the $bucket variable. 2. Run the Get-VBOAmazonS3Folder cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting S3 Compatible Folders

|  |  |
| --- | --- |
| This example shows how to get S3 Compatible folders.  |  | | --- | | $account = Get-VBOAmazonS3CompatibleAccount -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000"  $bucket = Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings $connection  Get-VBOAmazonS3Folder -Bucket $bucket -Name "Reports 10" |  Perform the following steps:   1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. Specify the necessary parameters. Save the result to the $connection variable. 3. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Specify the necessary parameters. Save the result to the $bucket variable.  1. Run the Get-VBOAmazonS3Folder cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. |

Related Commands

* [Get-VBOAmazonS3Account](get-vboamazons3account.md)
* [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md)
* [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md)
* [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md)

* [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
