---
title: "get-vbolicenseduser"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbolicenseduser.html"
last_updated: "4/11/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns licensed Veeam Backup for Microsoft 365 users.

Syntax

|  |
| --- |
| Get-VBOLicensedUser [-Organization <VBOOrganization>] [-Name <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns details on licensed Veeam Backup for Microsoft 365 users.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies an organization whose licensed users you want to get. The cmdlet will return a list of licensed users for the organization with the specified name. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | False | Named | False |
| Name | Specifies a name used to query a licensed user. The cmdlet will return information on the licensed user with the specified name. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOLicensedUser object that contains details on licensed Veeam Backup for Microsoft 365 users.

Example

Getting Information on Veeam Backup for Microsoft 365 Licensed User

This example shows how to get information on the John Smith licensed user from the Columbus organization.

|  |
| --- |
| $org = Get-VBOOrganization -Name "Columbus"  Get-VBOLicensedUser -Organization $org -Name "John Smith" |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Specify the Name parameter value. Save the result to the $org variable.
2. Run the Get-VBOLicensedUser cmdlet. Set the $org variable as the Organization parameter value. Specify the Name parameter value.

Related Commands

[Get-VBOOrganization](get-vboorganization.md)

Page updated 4/11/2025

Page content applies to build 8.3.0.2201
