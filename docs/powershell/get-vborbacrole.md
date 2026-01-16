---
title: "get-vborbacrole"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vborbacrole.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns settings of restore operator roles.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get a list of restore operator roles by the specified organization.

|  |
| --- |
| Get-VBORbacRole [-Organization <VBOOrganization>] [<CommonParameters>] |

* Get a restore operator role by ID.

|  |
| --- |
| Get-VBORbacRole -Id <Guid> [<CommonParameters>] |

* Get a restore operator role by role name.

|  |
| --- |
| Get-VBORbacRole -Name <String> [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of restore operator roles added to Veeam Backup for Microsoft 365.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will return restore operator roles that are added to the specified Microsoft organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | False | Named | True (ByValue) |
| Id | Specifies an ID of the restore operator role. The cmdlet will return the restore operator role with the specified ID. | Guid | True | Named | False |
| Name | Specifies a restore operator role name. The cmdlet will return the restore operator role with this name. | String | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBORbacRole object that contains a list of restore operator roles added to Veeam Backup for Microsoft 365.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Restore Operator Roles by Organization

|  |  |
| --- | --- |
| This example shows how to get restore operator roles added to the ABC organization.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBORbacRole -Organization $org |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Specify the Name parameter value. Save the result to the $org variable. 2. Run the Get-VBORbacRole cmdlet. Set the $org variable as the Organization parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Restore Operator Role by ID

|  |  |
| --- | --- |
| This command returns details of the f3f29c99-20b4-4eaa-9615-3b4c9d913a69 restore operator role.  |  | | --- | | Get-VBORbacRole -Id f3f29c99-20b4-4eaa-9615-3b4c9d913a69 | |

Related Commands

[Get-VBOOrganization](get-vboorganization.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
