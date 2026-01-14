---
title: "start-vbocopyjob"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/start-vbocopyjob.html"
last_updated: "5/8/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Starts backup copy jobs.

Syntax

|  |
| --- |
| Start-VBOCopyJob [-TeamsData] -Job <VBOCopyJob> [-RunAsync] [-Full] [<CommonParameters>] |

Detailed Description

This cmdlet allows you to start a backup copy job that is created or stopped.

Run the [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md) cmdlet to set the schedule for the job.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| TeamsData | Defines that the backup copy job will process backed-up Microsoft Teams data.  Default: False | SwitchParameter | False | Named | False |
| Job | Specifies a backup copy job that you want to start. | Accepts the VBOCopyJob object.  To get this object, run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet. | True | Named | True (ByValue) |
| RunAsync | Defines that the command returns immediately without waiting for the task to complete.  Default: False | SwitchParameter | False | Named | False |
| Full | Defines that the backup copy job will copy all backed-up Microsoft Teams data.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Starting Backup Copy Job

This example shows how to start the backup copy job.

|  |
| --- |
| $job = Get-VBOJob -Name "ABC Backup"  $copyjob = Get-VBOCopyJob -BackupJob $job  Start-VBOCopyJob -Job $copyjob |

Perform the following steps:

1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Specify the Name parameter value. Save the result to the $job variable.
2. Run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet. Set the $job variable as the BackupJob parameter value. Save the result to the $copyjob variable.
3. Run the Start-VBOCopyJob cmdlet. Set the $copyjob variable as the Job parameter value.

Related Commands

* [Get-VBOJob](get-vbojob.md)
* [Get-VBOCopyJob](get-vbocopyjob.md)
* [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md)

Page updated 5/8/2024

Page content applies to build 8.3.0.2201
