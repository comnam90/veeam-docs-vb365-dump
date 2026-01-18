---
title: "VBOCopyJob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbocopyjob.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBOCopyJob


Contains details about a backup copy job in Veeam Backup for Microsoft 365.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Job ID. |
| Name | String | Job name. |
| JobType | JobType | Job type. Possible values:   * Backup * Move * Remove * Copy * Retrieve * ChangeDataRetrievalAvailabilityPeriod * RemoveDataRetrieval * Migrate |
| Repository | [VBORepository](vborepository.md) | Details about a backup repository. |
| BackupJob | [VBOJob](vbojob.md) | Details about a backup job. |
| SchedulePolicy | [VBOCopyJobSchedulePolicy](vbocopyjobschedulepolicy.md) | Schedule settings for the job. |
| IsEnabled | Bool | If True, the job is enabled. |
| LastStatus | VBOJobStatus | Job status. Possible values:   * Stopped * Running * Success * Failed * Warning * NotConfigured |
| LastBackup | DateTime? | Date and time of the last successful run of the job. |
| LastRun | DateTime? | Date and time when the job was run for the last time. |
| NextRun | DateTime | Date and time of the next run of the job per schedule. |

Related Commands

* [Add-VBOCopyJob](add-vbocopyjob.md)
* [Get-VBOCopyJob](get-vbocopyjob.md)
* [Set-VBOCopyJob](set-vbocopyjob.md)
* [Remove-VBOCopyJob](remove-vbocopyjob.md)
* [Start-VBOCopyJob](start-vbocopyjob.md)
* [Stop-VBOCopyJob](stop-vbocopyjob.md)
* [Disable-VBOCopyJob](disable-vbocopyjob.md)
* [Enable-VBOCopyJob](enable-vbocopyjob.md)
* [Get-VBOJobSession](get-vbojobsession.md)


