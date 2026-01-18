---
title: "Remove-VBOJob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vbojob.html"
last_updated: "12/22/2025"
product_version: "8.3.0.2201"
---

# Remove-VBOJob


Short Description

Removes backup jobs.

Syntax

|  |
| --- |
| Remove-VBOJob -Job <VBOJob> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes a backup job from Veeam Backup for Microsoft 365.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup job that you want to remove. | Accepts the [VBOJob](vbojob.md) object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing Backup Job

This example shows how to remove a backup job without prompting a user whether he wants to continue.

|  |
| --- |
| $job = Get-VBOJob -Name "ABC Backup"  Remove-VBOJob -Job $job -Confirm:$false |

Perform the following steps:

1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Specify the Name parameter value. Save the result to the $job variable.
2. Run the Remove-VBOJob cmdlet. Set the $job variable as the Job parameter value. Set the false value for the Confirm parameter.

Related Commands

[Get-VBOJob](get-vbojob.md)


