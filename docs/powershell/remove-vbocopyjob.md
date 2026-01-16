---
title: "remove-vbocopyjob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vbocopyjob.html"
last_updated: "5/2/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Removes backup copy jobs.

Syntax

|  |
| --- |
| Remove-VBOCopyJob -Job <VBOCopyJob> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes a backup copy job from Veeam Backup for Microsoft 365.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup copy job that you want to remove. | Accepts the VBOCopyJob object.  To get this object, run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing Backup Copy Job

This example shows how to remove a backup copy job.

|  |
| --- |
| $copyjob = Get-VBOCopyJob -Id 8b6b539e-15cc-4ed6-bd1d-b8c7c918f413  Remove-VBOCopyJob -Job $copyjob |

Perform the following steps:

1. Run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet. Specify the Id parameter value. Save the result to the $copyjob variable.
2. Run the Remove-VBOCopyJob cmdlet. Set the $copyjob variable as the Job parameter value.

Related Commands

[Get-VBOCopyJob](get-vbocopyjob.md)

Page updated 5/2/2024

Page content applies to build 8.3.0.2201
