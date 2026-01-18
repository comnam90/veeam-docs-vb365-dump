---
title: "VBOCopyJobSchedulePolicy"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbocopyjobschedulepolicy.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBOCopyJobSchedulePolicy


Contains details about a backup copy job schedule settings.

| Property | Type | Description |
| --- | --- | --- |
| Type | VBOCopyJobFrequencyType | Type of the backup copy job schedule. Possible values:   * Immediate * Periodically * Daily |
| PeriodicallyEvery | VBOPeriodicInterval | Time interval between the job runs. Possible values:   * Minutes5 * Minutes10 * Minutes15 * Minutes30 * Hours1 * Hours2 * Hours4 * Hours8 * Hours12 |
| DailyTime | TimeSpan | Time to start the backup copy job. |
| DailyType | VBODailyType | Days when the backup copy job runs. Possible values:   * Everyday * Workdays * Weekends * Monday * Tuesday * Wednesday * Thursday * Friday * Saturday * Sunday |
| BackupWindowSettings | [VBOBackupWindowSettings](vbobackupwindowsettings.md)? | Details about a backup window. |

Related Commands

* [Add-VBOCopyJob](add-vbocopyjob.md)
* [Set-VBOCopyJob](set-vbocopyjob.md)
* [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md)
* [Set-VBOCopyJobSchedulePolicy](set-vbocopyjobschedulepolicy.md)


