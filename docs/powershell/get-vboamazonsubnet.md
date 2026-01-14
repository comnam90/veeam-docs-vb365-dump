---
title: "get-vboamazonsubnet"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboamazonsubnet.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns the Amazon archiver appliance subnet.

Syntax

|  |
| --- |
| Get-VBOAmazonSubnet -VPC <VBOAmazonVpc> [-Name <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns the VBOAmazonSubnet object.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| VPC | Specifies the Amazon VPC. | Accepts the VBOAmazonVpc object.  To get this object, run the [Get-VBOAmazonVPC](get-vboamazonvpc.md) cmdlet. | True | Named | False |
| Name | Specifies a name of the subnet. The cmdlet will return the subnet with this name. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonSubnet object.

Example

Getting Amazon Archiver Appliance Subnet

This example shows how to get the Amazon archiver appliance subnet.

|  |
| --- |
| $S3account = Get-VBOAmazonS3Account -AccessKey "?Iqws8NewidZydk"  $S3connection = New-VBOAmazonS3ConnectionSettings -Account $S3account -RegionType Global  $VPC = Get-VBOAmazonVPC -AmazonS3ConnectionSettings $S3connection -RegionId eu-central-1 -Name "VPCName"  Get-VBOAmazonSubnet -VPC $VPC -Name "SubnetName" |

Perform the following steps:

1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the AccessKey parameter value. Save the result to the $S3account variable.
2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Set the $S3account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $S3connection variable.
3. Run the [Get-VBOAmazonVPC](get-vboamazonvpc.md) cmdlet. Set the $S3connection variable as the AmazonS3ConnectionSettings parameter value. Specify the RegionId parameter value. Specify the Name parameter value. Save the result to the $VPC variable.
4. Run the Get-VBOAmazonSubnet cmdlet. Set the $VPC variable as the VPC parameter value. Specify the Name parameter value.

Related Commands

* [Get-VBOAmazonVPC](get-vboamazonvpc.md)
* [Get-VBOAmazonS3Account](get-vboamazons3account.md)
* [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
