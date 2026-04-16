---
title: "Stop-VBOJob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/stop-vbojob.html"
last_updated: "4/7/2026"
product_version: "8.4.0.1457"
---

# Stop-VBOJob


Short Description

Stops running backup jobs.

Syntax

|  |
| --- |
| Stop-VBOJob -Job <VBOJob> [-Force] [-RunAsync]  [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet stops a running backup job.

Parameters

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| Job | Specifies a backup job that you want to stop. | Accepts the [VBOJob](vbojob.md) object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | True (ByValue) |
| Force | Defines that the cmdlet will stop the specified backup job without waiting for the entire subprocesses to complete, for example, if the backup job gets stuck.  The cmdlet will prompt you to confirm the operation.  Default: False | SwitchParameter | False | Named | False |
| RunAsync | Defines that the command returns immediately without waiting for the task to complete.  Default: False | SwitchParameter | False | Named | False |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Stopping Backup Job

This example shows how to stop the backup job.

|  |
| --- |
| $job = Get-VBOJob -Name "ABC Backup"  Stop-VBOJob -Job $job |

Perform the following steps:

1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get the backup job that you want to stop. Save the result to the $job variable.
2. Run the Stop-VBOJob cmdlet with the $job variable.

Related Commands

[Get-VBOJob](get-vbojob.md)


