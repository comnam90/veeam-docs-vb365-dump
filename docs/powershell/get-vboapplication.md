---
title: "get-vboapplication"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboapplication.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns Microsoft Entra applications added to Microsoft 365 organizations.

Syntax

|  |
| --- |
| Get-VBOApplication -Organization <VBOOrganization> [-Id <Guid>] [-Name <String>] [-DisplayName <String>] [-Tag <String[]>] [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of Microsoft Entra applications added to Microsoft 365 organizations.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft 365 organization. The cmdlet will return an array of Microsoft Entra applications from this organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| Id | Specifies an ID of a Microsoft Entra application. The cmdlet will return the application with the specified ID. | Guid | False | Named | False |
| Name | Specifies a name of a Microsoft Entra application. The cmdlet will return the application with the specified name. | String | False | Named | False |
| DisplayName | Specifies a display name of a Microsoft Entra application. The cmdlet will return the application with the specified display name. | String | False | Named | False |
| Tag | Specifies an array of Microsoft Entra application tags. The cmdlet will return Microsoft Entra applications with these tags. | String[] | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOApplication object that contains Microsoft Entra applications added to Microsoft 365 organizations.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Microsoft Entra Applications

|  |  |
| --- | --- |
| This example shows how to get a list of all Microsoft Entra applications added to Microsoft 365 organizations.  |  | | --- | | $org = Get-VBOOrganization  Get-VBOApplication -Organization $org |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $org variable. 2. Run the Get-VBOApplication cmdlet. Set the $org variable as the Organization parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Microsoft Entra Application by Name

|  |  |
| --- | --- |
| This example shows how to get the SharePointOnlineApp Microsoft Entra application added to Microsoft 365 organizations.  |  | | --- | | $org = Get-VBOOrganization  Get-VBOApplication -Organization $org -Name SharePointOnlineApp |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $org variable. 2. Run the Get-VBOApplication cmdlet. Set the $org variable as the Organization parameter value. Specify the Name parameter value. |

Related Commands

[Get-VBOOrganization](get-vboorganization.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
