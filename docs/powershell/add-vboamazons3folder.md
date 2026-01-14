---
title: "add-vboamazons3folder"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboamazons3folder.html"
last_updated: "4/18/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Creates Amazon S3 folders.

Syntax

|  |
| --- |
| Add-VBOAmazonS3Folder -Bucket <VBOAmazonS3Bucket> -Name <String> [<CommonParameters>] |

Detailed Description

This cmdlet creates Amazon S3 folders.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Bucket | Specifies the Amazon S3 bucket. The cmdlet will add Amazon S3 folder to this bucket. | Accepts the VBOAmazonS3Bucket object.  To get this object, run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. | True | Named | False |
| Name | Specifies a name of the Amazon S3 folder. The cmdlet will create the Amazon S3 folder with this name. | String | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3Folder object that contains an array of Amazon S3 folders.

Example

Creating Amazon S3 Folder

This example shows how to create an Amazon S3 folder.

|  |
| --- |
| $account = Get-VBOAmazonS3Account -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3ConnectionSettings -Account $account -RegionType Global  $bucket = Get-VBOAmazonS3Bucket -AmazonS3ConnectionSettings $connection -RegionId eu-north-1  Add-VBOAmazonS3Folder -Bucket $bucket -Name "February\_reports" |

Perform the following steps:

1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable.
2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Specify the necessary parameters. Save the result to the $connection variable.

1. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Specify the necessary parameters. Save the result to the $bucket variable.
2. Run the Add-VBOAmazonS3Folder cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value.

Related Commands

* [Get-VBOAmazonS3Account](get-vboamazons3account.md)
* [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md)
* [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md)

Page updated 4/18/2024

Page content applies to build 8.3.0.2201
