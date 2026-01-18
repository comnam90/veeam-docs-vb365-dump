---
title: "Get-VBOAmazonVPC"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboamazonvpc.html"
last_updated: "12/18/2025"
product_version: "8.3.0.2201"
---

# Get-VBOAmazonVPC


Short Description

Returns the Amazon Virtual Private Cloud (Amazon VPC).

Syntax

|  |
| --- |
| Get-VBOAmazonVPC -AmazonS3ConnectionSettings <VBOAmazonS3ConnectionSettings> [-Name <String>] -RegionId <String> [<CommonParameters>] |

Detailed Description

This cmdlet returns the [VBOAmazonVPC](vboamazonvpc.md) object.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| AmazonS3ConnectionSettings | Specifies an active session with Amazon S3 object storage repository. | Accepts the [VBOAmazonS3ConnectionSettings](vboamazons3connectionsettings.md) object.  To create this object, run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. | True | Named | False |
| Name | Specifies a name of the Amazon VPC. The cmdlet will return the Amazon VPC with this name. | String | False | Named | False |
| RegionId | Specifies a region of Amazon S3 object storage repository.  For example, us-east-1.  For more information, see [this Amazon article](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.RegionsAndAvailabilityZones.html). | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAmazonVPC](vboamazonvpc.md) object.

Example

Getting Amazon VPC

This example shows how to get the Amazon Virtual Private Cloud (Amazon VPC).

|  |
| --- |
| $S3account = Get-VBOAmazonS3Account -AccessKey "?Iqws8NewidZydk"  $S3connection = New-VBOAmazonS3ConnectionSettings -Account $S3account -RegionType Global  Get-VBOAmazonVPC -AmazonS3ConnectionSettings $S3connection -RegionId eu-central-1 -Name "VPCName" |

Perform the following steps:

1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the AccessKey parameter value. Save the result to the $S3account variable.
2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Set the $S3account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $S3connection variable.
3. Run the Get-VBOAmazonVPC cmdlet. Specify the following settings:

* Set the $S3connection variable as the AmazonS3ConnectionSettings parameter value.
* Specify the RegionId parameter value.
* Specify the Name parameter value.

Related Commands

* [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md)
* [Get-VBOAmazonS3Account](get-vboamazons3account.md)


