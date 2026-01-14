---
title: "remove-vborbacrole"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vborbacrole.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Removes restore operator roles from Veeam Backup for Microsoft 365.

Syntax

|  |
| --- |
| Remove-VBORbacRole -Role <VBOOperatorRole> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes the specified restore operator role from Veeam Backup for Microsoft 365.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Role | Specifies a restore operator role that you want to remove. | Accepts the VBOOperatorRole object.  To get this object, run the [Get-VBORbacRole](get-vborbacrole.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing Restore Operator Role

This example shows how to remove the f3f29c99-20b4-4eaa-9615-3b4c9d913a69 restore operator role.

|  |
| --- |
| $role = Get-VBORbacRole -Id f3f29c99-20b4-4eaa-9615-3b4c9d913a69  Remove-VBORbacRole -Role $role -Confirm |

Perform the following steps:

1. Run the [Get-VBORbacRole](get-vborbacrole.md) cmdlet. Specify the Id parameter value. Save the result to the $role variable.
2. Run the Remove-VBORbacRole cmdlet. Specify the following settings:

* Set the $role variable as the Role parameter value.
* Provide the Confirm parameter.

Related Commands

[Get-VBORbacRole](get-vborbacrole.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
