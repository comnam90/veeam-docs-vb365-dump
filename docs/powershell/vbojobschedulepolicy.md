---
title: "VBOJobSchedulePolicy"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbojobschedulepolicy.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBOJobSchedulePolicy


Contains details about a backup job schedule settings.

| Property | Type | Description |
| --- | --- | --- |
| Type | VBOJobFrequencyType | Type of the backup job schedule. Possible values:   * Periodically * Daily |
| PeriodicallyEvery | VBOPeriodicInterval | Time interval between the job runs. Possible values:   * Minutes5 * Minutes10 * Minutes15 * Minutes30 * Hours1 * Hours2 * Hours4 * Hours8 * Hours12 |
| PeriodicallyOffsetMinutes | Int | Offset within an hour in minutes to start several backup jobs according to the periodic schedule. |
| DailyType | VBODailyType | Days when the backup job runs. Possible values:   * Everyday * Workdays * Weekends * Monday * Tuesday * Wednesday * Thursday * Friday * Saturday * Sunday |
| DailyTime | TimeSpan | Time to start the backup job. |
| BackupWindowSettings | [VBOBackupWindowSettings](vbobackupwindowsettings.md) | Details about a backup window. |
| PeriodicallyWindowSettings | [VBOBackupWindowSettings](vbobackupwindowsettings.md) | Details about a backup window. |
| RetryEnabled | Bool | If True, Veeam Backup for Microsoft 365 restarts the backup job if it fails for some reason. |
| RetryNumber | Int | Number of attempts to restart the backup job. |
| RetryWaitInterval | Int | Time intervals between the job retry attempts in minutes. |
| EnableSchedule | Bool | If True, the backup job schedule is enabled. |

Related Commands

* [Add-VBOJob](add-vbojob.md)
* [Set-VBOJob](set-vbojob.md)
* [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md)
* [Set-VBOJobSchedulePolicy](set-vbojobschedulepolicy.md)


