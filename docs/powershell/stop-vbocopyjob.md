---
title: "Stop-VBOCopyJob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/stop-vbocopyjob.html"
last_updated: "4/7/2026"
product_version: "8.4.0.1457"
---

# Stop-VBOCopyJob


Short Description

Stops running backup copy jobs.

Syntax

|  |
| --- |
| Stop-VBOCopyJob -Job <VBOCopyJob> [-Force] [-RunAsync]  [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet stops a running backup copy job.

Parameters

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| Job | Specifies a backup copy job that you want to stop. | Accepts the [VBOCopyJob](vbocopyjob.md) object.  To get this object, run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet. | True | Named | True (ByValue) |
| Force | Defines that the cmdlet will stop the specified backup copy job without waiting for the entire subprocesses to complete, for example, if the backup copy job gets stuck.  The cmdlet will prompt you to confirm the operation.  Default: False | SwitchParameter | False | Named | False |
| RunAsync | Defines that the command returns immediately without waiting for the task to complete.  Default: False | SwitchParameter | False | Named | False |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Stopping Backup Copy Job

This example shows how to stop the backup copy job.

|  |
| --- |
| $job = Get-VBOJob -Name "ABC Backup"  $copyjob = Get-VBOCopyJob -BackupJob $job  Stop-VBOCopyJob -Job $copyjob |

Perform the following steps:

1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Specify the Name parameter value. Save the result to the $job variable.
2. Run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet. Set the $job variable as the BackupJob parameter value. Save the result to the $copyjob variable.
3. Run the Stop-VBOCopyJob cmdlet. Set the $copyjob variable as the Job parameter value.

Related Commands

* [Get-VBOJob](get-vbojob.md)
* [Get-VBOCopyJob](get-vbocopyjob.md)


