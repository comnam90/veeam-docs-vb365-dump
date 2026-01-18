---
title: "Start-VBOJob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/start-vbojob.html"
last_updated: "12/22/2025"
product_version: "8.3.0.2201"
---

# Start-VBOJob


Short Description

Starts backup jobs.

Syntax

|  |
| --- |
| Start-VBOJob -Job <VBOJob> [-RunAsync] [-Full] [<CommonParameters>] |

Detailed Description

This cmdlet allows you to start a created or stopped backup job.

Run the [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md) cmdlet to set the schedule for the job.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup job that you want to start. | Accepts the [VBOJob](vbojob.md) object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | True (ByValue) |
| RunAsync | Defines that the command returns immediately without waiting for the task to complete.  Default: False | SwitchParameter | False | Named | False |
| Full | Defines that the backup job session is considered a full run.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Starting Backup Job

|  |  |
| --- | --- |
| This example shows how to start the backup job.  |  | | --- | | $job = Get-VBOJob -Name "Backup Daily"  Start-VBOJob -Job $job |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get the backup job that you want to start. Save the result to the $job variable. 2. Run the Start-VBOJob cmdlet with the $job variable. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Starting Full Run

|  |  |
| --- | --- |
| This example shows how to start a full run for the backup job.  |  | | --- | | $job = Get-VBOJob -Name "Full Backup"  Start-VBOJob -Job $job -Full:$true |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get the backup job that you want to start. Save the result to the $job variable. 2. Run the Start-VBOJob cmdlet with the $job variable. Set the true value for the Full parameter. |

Related Commands

* [Get-VBOJob](get-vbojob.md)
* [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md)


