---
title: "add-vbocopyjob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vbocopyjob.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Creates a backup copy job.

Syntax

|  |
| --- |
| Add-VBOCopyJob -Repository <VBORepository> -BackupJob <VBOJob> [-SchedulePolicy <VBOCopyJobSchedulePolicy>] [<CommonParameters>] |

Detailed Description

This cmdlet creates a backup copy job that will protect backups created by Veeam Backup for Microsoft 365 using the specified backup job. The backup copy job will copy backed-up data to one of the following cloud-based or on-premises object storage repositories:

* Azure Blob Storage Hot access tier
* Azure Blob Storage Cool access tier
* Azure Blob Storage Archive access tier
* Amazon S3 Standard storage class
* Amazon S3 Standard-Infrequent Access storage class
* Amazon S3 One Zone-Infrequent Access storage class
* all Amazon S3 Glacier storage classes: Glacier Instant Retrieval, Glacier Flexible Retrieval, Glacier Deep Archive
* S3 Compatible object storage repository (if applicable)

|  |
| --- |
| ![Add-VBOCopyJob](images/icon_note.webp) Note |
| Before creating a backup copy job, make sure you are familiar with the following restrictions:   * Only one backup copy job can be created per backup job. * Object storage repository where you store your backups and a target object storage repository for backup copies must be located on the same backup proxy server or backup proxy pool and have the same retention type. * For a target object storage repository for backup copies, the immutability period equal to the retention period must be configured. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Repository | Specifies an object storage repository. Veeam Backup for Microsoft 365 will copy backed-up data to this object storage repository. | Accepts the VBORepository object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | False |
| BackupJob | Specifies a backup job for which you want to create backup copies. | Accepts the VBOJob object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | False |
| SchedulePolicy | Specifies schedule settings for a backup copy job.  Default: Immediate | Accepts the VBOCopyJobSchedulePolicy object.  To create this object, run the [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOCopyJob object that contains settings for a backup copy job.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Creating Backup Copy Job

|  |  |
| --- | --- |
| This example shows how to create a backup copy job for the backup job with the name ABC Backup.  |  | | --- | | $job = Get-VBOJob -Name "ABC Backup"  $repository = Get-VBORepository -Name "Azure Archive Storage"  Add-VBOCopyJob -Repository $repository -BackupJob $job |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Specify the Name parameter value. Save the result to the $job variable. 2. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable. 3. Run the Add-VBOCopyJob cmdlet. Set the $job variable as the BackupJob parameter value and the $repository variable as the Repository parameter value.   The cmdlet output will contain the following details on the backup copy job: Id, Name, Description, Repository, BackupJob, SchedulePolicy, IsEnabled, LastStatus, LastRun and NextRun. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Creating Backup Copy Job and Setting Schedule

|  |  |
| --- | --- |
| This example shows how to create a backup copy job for the backup job with the name ABC Backup and configure a backup copy job schedule. A backup copy job schedule will have the following settings:   * A backup copy job will run everyday at 10 AM. * A backup copy job will stop if its processing exceeds the allowed backup window.   |  | | --- | | $job = Get-VBOJob -Name "ABC Backup"  $repository = Get-VBORepository -Name "Azure Archive Storage"  $bwindow = New-VBOBackupWindowSettings -FromDay Monday -FromHour 8 -ToDay Sunday -ToHour 17 -Enabled:$true  $daily = New-VBOCopyJobSchedulePolicy -Type Daily -DailyType Everyday -DailyTime 10:00:00 -BackupWindowSettings $bwindow  Add-VBOCopyJob -Repository $repository -BackupJob $job -SchedulePolicy $daily |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Specify the Name parameter value. Save the result to the $job variable. 2. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable. 3. Run the [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md) cmdlet to create a backup window within which the backup copy job must be completed. Save the result to the $bwindow variable. 4. Run the [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md) cmdlet with the $bwindow variable to set the job schedule. Save the result to the $daily variable. 5. Run the Add-VBOCopyJob cmdlet. Specify the following settings:  * Set the $job variable as the BackupJob parameter value. * Set the $repository variable as the Repository parameter value. * Set the $daily variable as the SchedulePolicy parameter value.   The cmdlet output will contain the following details on the backup copy job: Id, Name, Description, Repository, BackupJob, SchedulePolicy, IsEnabled, LastStatus, LastRun and NextRun. |

Related Commands

* [Get-VBOJob](get-vbojob.md)
* [Get-VBORepository](get-vborepository.md)
* [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md)
* [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
