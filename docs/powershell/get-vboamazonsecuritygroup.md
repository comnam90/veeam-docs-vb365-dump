---
title: "Get-VBOAmazonSecurityGroup"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboamazonsecuritygroup.html"
last_updated: "12/18/2025"
product_version: "8.3.0.2201"
---

# Get-VBOAmazonSecurityGroup


Short Description

Returns a security group that will be associated with the Amazon archiver appliance.

Syntax

|  |
| --- |
| Get-VBOAmazonSecurityGroup -VPC <VBOAmazonVpc> [-Name <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns the [VBOAmazonSecurityGroup](vboamazonsecuritygroup.md) object.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| VPC | Specifies the Amazon VPC. | Accepts the [VBOAmazonVpc](vboamazonvpc.md) object.  To get this object, run the [Get-VBOAmazonVPC](get-vboamazonvpc.md) cmdlet. | True | Named | False |
| Name | Specifies a name of the security group. The cmdlet will return the security group with this name. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAmazonSecurityGroup](vboamazonsecuritygroup.md) object that will be associated with the Amazon archiver appliance.

Example

Getting Security Group

This example shows how to get the security group that will be associated with the Amazon archiver appliance.

|  |
| --- |
| $S3account = Get-VBOAmazonS3Account -AccessKey "?Iqws8NewidZydk"  $S3connection = New-VBOAmazonS3ConnectionSettings -Account $S3account -RegionType Global  $VPC = Get-VBOAmazonVPC -AmazonS3ConnectionSettings $S3connection -RegionId eu-central-1 -Name "VPCName"  Get-VBOAmazonSecurityGroup -VPC $VPC -Name "SecurityGroupName" |

Perform the following steps:

1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the AccessKey parameter value. Save the result to the $S3account variable.
2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Set the $S3account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $S3connection variable.
3. Run the [Get-VBOAmazonVPC](get-vboamazonvpc.md) cmdlet. Set the $S3connection variable as the AmazonS3ConnectionSettings parameter value. Specify the RegionId parameter value. Specify the Name parameter value. Save the result to the $VPC variable.
4. Run the Get-VBOAmazonSecurityGroup cmdlet. Set the $VPC variable as the VPC parameter value. Specify the Name parameter value.

Related Commands

* [Get-VBOAmazonVPC](get-vboamazonvpc.md)
* [Get-VBOAmazonS3Account](get-vboamazons3account.md)
* [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md)


