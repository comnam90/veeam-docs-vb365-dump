---
title: "Remove-VBOExcludedBackupItem"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vboexcludedbackupitem.html"
last_updated: "12/23/2025"
product_version: "8.3.0.2201"
---

# Remove-VBOExcludedBackupItem


Short Description

Removes objects from a list of exclusions specified for a backup job.

Syntax

|  |
| --- |
| Remove-VBOExcludedBackupItem -Job <VBOJob> -BackupItem <VBOBackupItem[]> [<CommonParameters>] |

Detailed Description

This cmdlet removes objects from a list of exclusions that is specified for a backup job.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup job. The cmdlet will remove objects from the exclusions list that is specified for this job. | Accepts the [VBOJob](vbojob.md) object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | False |
| BackupItem | Specifies an array of objects that you want to remove from the exclusions list. | Accepts the [VBOBackupItem](vbobackupitem.md)[] object.  To get this object, run the [Get-VBOBackupItem](get-vbobackupitem.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing Items from List of Exclusions

This example shows how to remove items from a list of exclusions that is added to the Yearly Backup job.

|  |
| --- |
| $job = Get-VBOJob -Name "Yearly Backup"  $item = Get-VBOBackupItem -Job $job  Remove-VBOExcludedBackupItem -Job $job -BackupItem $item |

Perform the following steps:

1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to specify a job from which you want to get items. Set Yearly Backup as the Name parameter value. Save the result to the $job variable.
2. Run the [Get-VBOBackupItem](get-vbobackupitem.md) cmdlet. Set the $job variable as the Job parameter value. Save the result to the $item variable.
3. Run the Remove-VBOExcludedBackupItem cmdlet. Set the $job variable as the Job parameter value. Set the $item variable as the BackupItem parameter value.

Related Commands

* [Get-VBOJob](get-vbojob.md)
* [Get-VBOBackupItem](get-vbobackupitem.md)


