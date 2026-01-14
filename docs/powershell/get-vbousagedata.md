---
title: "get-vbousagedata"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbousagedata.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns information on the used space in backup repositories.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get information on the used space in the specified backup repository.

|  |
| --- |
| Get-VBOUsageData -Repository <VBORepository> [<CommonParameters>] |

* Get information on the used space by the specified organization and backup repository.

|  |
| --- |
| Get-VBOUsageData -Repository <VBORepository> -Organization <VBOOrganization> [<CommonParameters>] |

* Get information on the used space by the specified organization.

|  |
| --- |
| Get-VBOUsageData -Organization <VBOOrganization> [<CommonParameters>] |

Detailed Description

This cmdlet returns a representation entity of a used repository space by an organization or a representation of an organizations used data space in all used backup repositories.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Repository | Specifies a backup repository. The cmdlet will return information on data usage in this backup repository. | Accepts the VBORepository object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | False |
| Organization | Specifies a Microsoft organization. The cmdlet will return information on data usage by this organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Information About Data Usage on Specific Backup Repository

|  |  |
| --- | --- |
| This example shows how to get information on the data usage for a backup repository with the name Repository1.  |  | | --- | | $repository = Get-VBORepository -Name "Repository1"  Get-VBOUsageData -Repository $repository |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get a backup repository with the name Repository1. Save the result to the $repository variable. 2. Run the Get-VBOUsageData cmdlet with the $repository variable to get the data usage information for the specified repository. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Information About Data Usage by Specific Organization

|  |  |
| --- | --- |
| This example shows how to get information on the data usage by an organization with the name Organization1 in a backup repository with the name Repository1.  |  | | --- | | $repository = Get-VBORepository -Name "Repository1"  $organization = Get-VBOOrganization -Name "Organization1"  Get-VBOUsageData -Repository $repository -Organization $organization |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get to get a backup repository with the name Repository1. Save the result to the $repository variable. 2. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get an organization with the name Organization1. Save the result to the $organization variable. 3. Run the Get-VBOUsageData cmdlet with the $repository and $organization variables to get the data usage information. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Information About Data Usage

|  |  |
| --- | --- |
| This example shows how to get information on the data usage by an organization with the name Organization1.  |  | | --- | | $organization = Get-VBOOrganization -Name "Organization1"  Get-VBOUsageData -Organization $organization |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get an organization with the name Organization1. Save the result to the $organization variable. 2. Run the Get-VBOUsageData cmdlet with the $organization variable to get the data usage information. |

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBORepository](get-vborepository.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
