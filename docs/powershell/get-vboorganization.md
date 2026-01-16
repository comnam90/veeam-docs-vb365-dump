---
title: "get-vboorganization"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboorganization.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns Microsoft organizations added to the Veeam Backup for Microsoft 365 infrastructure.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get Microsoft organizations added to the Veeam Backup for Microsoft 365 infrastructure by name.

|  |
| --- |
| Get-VBOOrganization [-Name <String>] [<CommonParameters>] |

* Get Microsoft organizations added to the Veeam Backup for Microsoft 365 infrastructure by ID.

|  |
| --- |
| Get-VBOOrganization -Id <Guid> [<CommonParameters>] |

Detailed Description

This cmdlet returns Microsoft organizations added to the Veeam Backup for Microsoft 365 infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Name | Specifies a name of the Microsoft organization. The cmdlet will return the Microsoft organization with this name. | String | False | Named | False |
| Id | Specifies an ID of the Microsoft organization. The cmdlet will return the organization with this ID. | Guid | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOOrganization object that contains settings of Microsoft organizations added to the Veeam Backup for Microsoft 365 infrastructure.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Microsoft Organizations Added to Veeam Backup for Microsoft 365 Infrastructure

|  |  |
| --- | --- |
| This command returns all Microsoft organizations that are added to the Veeam Backup for Microsoft 365 infrastructure.  |  | | --- | | Get-VBOOrganization | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Microsoft Organization by ID

|  |  |
| --- | --- |
| This command returns the 47972f7d-05c4-43b5-95f7-60735ee56006 Microsoft organization.  |  | | --- | | Get-VBOOrganization -Id 47972f7d-05c4-43b5-95f7-60735ee56006 | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Microsoft Organization by Name

|  |  |
| --- | --- |
| This command returns the Atlanta Microsoft organization.  |  | | --- | | Get-VBOOrganization -Name "Atlanta" | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Getting Microsoft Organization by Name [Using Wildcards]

|  |  |
| --- | --- |
| This command returns all Microsoft organizations with a name starting with Columb.  |  | | --- | | Get-VBOOrganization -Name "Columb\*" | |

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
