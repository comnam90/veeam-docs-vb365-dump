---
title: "remove-vbobackupitem"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vbobackupitem.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Removes an object from a backup job.

Syntax

|  |
| --- |
| Remove-VBOBackupItem -Job <VBOJob> -BackupItem <VBOBackupItem[]> [<CommonParameters>] |

Detailed Description

This cmdlet removes an object from a backup job.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup job. The cmdlet will remove an object from this backup job. | Accepts the VBOJob object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | False |
| BackupItem | Specifies an array of objects. The cmdlet will remove these objects from the specified backup job. | Accepts the VBOBackupItem[] object.  To get this object, run the [Get-VBOBackupItem](get-vbobackupitem.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Removing Backup Item by Name

|  |  |
| --- | --- |
| This example shows how to remove a Microsoft Exchange or Microsoft SharePoint object from the scope of the TestJob backup job even if this object is no longer available in Microsoft organization.  |  | | --- | | $job = Get-VBOJob -Name "TestJob"  $item = Get-VBOBackupItem -Job $job -Name "ObjectToRemove"  Remove-VBOBackupItem -Job $job -BackupItem $item |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Specify the Name parameter value. Save the result to the $job variable. 2. Run the [Get-VBOBackupItem](get-vbobackupitem.md) cmdlet. Set the $job variable as the Job parameter value and specify the Name parameter value to select the item in the backup job. Save the result to the $item variable. 3. Run the Remove-VBOBackupItem cmdlet with the $job and $item variables to remove the selected object from the specified backup job. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Removing User Backup Item

|  |  |
| --- | --- |
| This example shows how to remove an organization user UserAlpha backup item from the TestJob backup job.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC Company"  $user = Get-VBOOrganizationUser -Organization $org -DisplayName "UserAlpha"  $backupItemUser = New-VBOBackupItem -User $user -Mailbox:$True -ArchiveMailbox:$false -OneDrive:$false  $job = Get-VBOJob -Name "TestJob"  Remove-VBOBackupItem -Job $job -BackupItem $backupItemUser |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet to get an organization. Save the result to the $org variable. 2. Run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet to get an organization user. Save the result to the $user variable. 3. Run the [New-VBOBackupItem](new-vbobackupitem.md) cmdlet to select the item in the backup job. Save the result to the $backupItemUser variable. 4. Run the [Get-VBOJob](get-vbojob.md) cmdlet to select the backup job for modification. Save the result to the $job variable. 5. Run the Remove-VBOBackupItem cmdlet with the $job and $backupItemUser variables to remove the selected user from the specified backup job. |

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationUser](get-vboorganizationuser.md)
* [New-VBOBackupItem](new-vbobackupitem.md)
* [Get-VBOJob](get-vbojob.md)
* [Get-VBOBackupItem](get-vbobackupitem.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
