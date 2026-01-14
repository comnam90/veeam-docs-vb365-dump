---
title: "set-vbocopyjob"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbocopyjob.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies settings of a backup copy job.

Syntax

|  |
| --- |
| Set-VBOCopyJob -Job <VBOCopyJob> [-Repository <VBORepository>] [-SchedulePolicy <VBOCopyJobSchedulePolicy>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies settings of a backup copy job. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup copy job whose settings you want to modify. | Accepts the VBOCopyJob object.  To get this object, run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet. | True | Named | True (ByValue) |
| Repository | Specifies an object storage repository. Veeam Backup for Microsoft 365 uses this object storage repository as a target for backup copy jobs. | Accepts the VBORepository object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | False | Named | False |
| SchedulePolicy | Specifies schedule settings for a backup copy job. | Accepts the VBOCopyJobSchedulePolicy object.  To create this object, run the [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOCopyJob object that contains settings for a backup copy job.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Object Storage Repository for Backup Copy Job

|  |  |
| --- | --- |
| This example shows how to change a target object storage repository for the backup copy job created for the backup job with the name ABC Backup.  |  | | --- | | $job = Get-VBOJob -Name "ABC Backup"  $copyjob = Get-VBOCopyJob -BackupJob $job  $repository = Get-VBORepository -Name "Amazon S3 Glacier Flexible Retrieval"  Set-VBOCopyJob -Job $copyjob -Repository $repository |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Specify the Name parameter value. Save the result to the $job variable. 2. Run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet. Set the $job variable as the BackupJob parameter value. Save the result to the $copyjob variable. 3. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable. 4. Run the Set-VBOCopyJob cmdlet. Specify the following settings:  * Set the $copyjob variable as the Job parameter value. * Set the $repository variable as the Repository parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Setting New Schedule for Backup Copy Job

|  |  |
| --- | --- |
| This example shows how to set new schedule settings for a backup copy job. A backup copy job will run every 8 hours.  |  | | --- | | $copyjob = Get-VBOCopyJob -Id 8b6b539e-15cc-4ed6-bd1d-b8c7c918f413  $every8hours = New-VBOCopyJobSchedulePolicy -Type Periodically -PeriodicallyEvery Hours8  Set-VBOCopyJob -Job $copyjob -SchedulePolicy $every8hours |  Perform the following steps:   1. Run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet to get a backup copy job whose schedule settings you want to configure. Specify the Id parameter value. Save the result to the $copyjob variable. 2. Run the [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md) cmdlet to set the job schedule. Specify the necessary parameters. Save the result to the $every8hours variable. 3. Run the Set-VBOCopyJob cmdlet. Set the $copyjob variable as the Job parameter value. Set the $every8hours variable as the SchedulePolicy parameter value. |

Related Commands

* [Get-VBOJob](get-vbojob.md)
* [Get-VBOCopyJob](get-vbocopyjob.md)
* [Get-VBORepository](get-vborepository.md)
* [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
