---
title: "Add-VBOBackupItem"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vbobackupitem.html"
last_updated: "12/23/2025"
product_version: "8.3.0.2201"
---

# Add-VBOBackupItem


Short Description

Adds a list of objects to a backup job.

Syntax

|  |
| --- |
| Add-VBOBackupItem -Job <VBOJob> -BackupItem <VBOBackupItem[]> [<CommonParameters>] |

Detailed Description

This cmdlet adds a list of objects to a backup job. The job will process these objects.

|  |
| --- |
| ![Add-VBOBackupItem](images/icon_note.webp) Note |
| Before you add an object to a backup job, consider the following restrictions:   * Only one job can back up an entire organization. * Several jobs cannot back up the same object. * If you add an object that has already been added to the backup job again, a new object will replace the old object. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup job. The cmdlet will add an array of objects to this job. | Accepts the [VBOJob](vbojob.md) object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | False |
| BackupItem | Specifies an array of objects. The cmdlet will add them to a list of included objects. | Accepts the [VBOBackupItem](vbobackupitem.md)[] object.   * To get this object, run the [Get-VBOBackupItem](get-vbobackupitem.md) cmdlet. * To create this object, run the [New-VBOBackupItem](new-vbobackupitem.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Adding User Backup Item to Backup Job

This example shows how to add an organization user UserAlpha backup item to the TestJob backup job.

|  |
| --- |
| $org = Get-VBOOrganization -Name "ABC Company"  $user = Get-VBOOrganizationUser -Organization $org -DisplayName "UserAlpha"  $backupItemUser = New-VBOBackupItem -User $user -Mailbox:$True -ArchiveMailbox:$false -OneDrive:$false  $job = Get-VBOJob -Name "TestJob"  Add-VBOBackupItem -Job $job -BackupItem $backupItemUser |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet to get an organization. Save the result to the $org variable.
2. Run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet to get an organization user. In this case we will use it as a backup item. Save the result to the $user variable.
3. Run the [New-VBOBackupItem](new-vbobackupitem.md) cmdlet to select the item for the backup job. Save the result to the $backupItemUser variable.
4. Run the [Get-VBOJob](get-vbojob.md) cmdlet to select the backup job for modification. Save the result to the $job variable.
5. Run the Add-VBOBackupItem cmdlet with the $job and $backupItemUser variables to add the selected user to the specified backup job.

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationUser](get-vboorganizationuser.md)
* [New-VBOBackupItem](new-vbobackupitem.md)

* [Get-VBOBackupItem](get-vbobackupitem.md)

* [Get-VBOJob](get-vbojob.md)


