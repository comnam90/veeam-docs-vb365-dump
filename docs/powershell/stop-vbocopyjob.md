---
title: "stop-vbocopyjob"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/stop-vbocopyjob.html"
last_updated: "6/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Stops running backup copy jobs.

Syntax

|  |
| --- |
| Stop-VBOCopyJob -Job <VBOCopyJob> [-Force] [-RunAsync] [<CommonParameters>] |

Detailed Description

This cmdlet stops a running backup copy job.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup copy job that you want to stop. | Accepts the VBOCopyJob object.  To get this object, run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet. | True | Named | True (ByValue) |
| Force | Defines that the cmdlet will stop the specified backup copy job without waiting for the entire subprocesses to complete, for example, if the backup copy job gets stuck.  The cmdlet will prompt you to confirm the operation.  Default: False | SwitchParameter | False | Named | False |
| RunAsync | Defines that the command returns immediately without waiting for the task to complete.  Default: False | SwitchParameter | False | Named | False |

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

Page updated 6/10/2025

Page content applies to build 8.3.0.2201
