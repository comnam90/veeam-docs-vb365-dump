---
title: "remove-vboorganization"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vboorganization.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Removes Microsoft organizations from the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| ![Remove-VBOOrganization](images/icon_important.webp) Important |
| Before removing an organization, make sure all jobs that are configured for that organization are set to the Disabled state. |

Syntax

|  |
| --- |
| Remove-VBOOrganization -Organization <VBOOrganization> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes Microsoft organizations from the Veeam Backup for Microsoft 365 infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies an organization that you want to remove. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing Microsoft Organization

This example shows how to remove the Dev Community organization from the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| $org = Get-VBOOrganization -Name "Dev Community"  Remove-VBOOrganization -Organization $org |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $org variable.
2. Run the Remove-VBOOrganization cmdlet. Set the $org variable as the Organization parameter value.

Related Commands

[Get-VBOOrganization](get-vboorganization.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
