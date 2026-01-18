---
title: "VBOJob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbojob.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOJob


Contains details about a job in Veeam Backup for Microsoft 365.

| Property | Type | Description |
| --- | --- | --- |
| Organization | [VBOOrganization](vboorganization.md) | Details about a Microsoft organization. |
| Name | String | Job name. |
| JobType | JobType | Job type. Possible values:   * Backup * Move * Remove * Copy * Retrieve * ChangeDataRetrievalAvailabilityPeriod * RemoveDataRetrieval * Migrate |
| Description | String | Job description. |
| JobBackupType | VBOJobBackupType | Backup job type. Possible values:   * EntireOrganization * SelectedItems |
| SelectedItems | [VBOBackupItem](vbobackupitem.md)[] | Array of objects that the backup job backs up. |
| ExcludedItems | [VBOBackupItem](vbobackupitem.md)[] | Array of objects that the backup job does not back up. |
| SelectedOneDriveFolders | String[] | Array of OneDrive folders that the backup job backs up. |
| ExcludedOneDriveFolders | String[] | Array of OneDrive folders that the backup job does not back up. |
| Repository | [VBORepository](vborepository.md) | Details about a backup repository. |
| LastStatus | VBOJobStatus | Job status. Possible values:   * Stopped * Running * Success * Failed * Warning * NotConfigured |
| LastRun | DateTime? | Date and time when the job was run for the last time. |
| NextRun | DateTime | Date and time of the next run of the job per schedule. |
| LastBackup | DateTime? | Date and time of the last successful run of the job. |
| IsEnabled | Bool | If True, the job is enabled. |
| SchedulePolicy | [VBOJobSchedulePolicy](vbojobschedulepolicy.md) | Schedule settings for the job. |
| Id | GUID | Job ID. |

Related Commands

* [Add-VBOBackupItem](add-vbobackupitem.md)
* [Get-VBOBackupItem](get-vbobackupitem.md)
* [Remove-VBOBackupItem](remove-vbobackupitem.md)
* [Get-VBOExcludedBackupItem](get-vboexcludedbackupitem.md)
* [Add-VBOExcludedBackupItem](add-vboexcludedbackupitem.md)
* [Remove-VBOExcludedBackupItem](remove-vboexcludedbackupitem.md)
* [Add-VBOJob](add-vbojob.md)
* [Get-VBOJob](get-vbojob.md)
* [Set-VBOJob](set-vbojob.md)
* [Remove-VBOJob](remove-vbojob.md)
* [Start-VBOJob](start-vbojob.md)
* [Stop-VBOJob](stop-vbojob.md)
* [Disable-VBOJob](disable-vbojob.md)
* [Enable-VBOJob](enable-vbojob.md)
* [Add-VBOCopyJob](add-vbocopyjob.md)
* [Get-VBOCopyJob](get-vbocopyjob.md)
* [Get-VBORestorePoint](get-vborestorepoint.md)


