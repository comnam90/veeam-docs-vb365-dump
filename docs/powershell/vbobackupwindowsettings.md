---
title: "VBOBackupWindowSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbobackupwindowsettings.html"
last_updated: "1/6/2026"
product_version: "8.3.0.2201"
---

# VBOBackupWindowSettings


Contains details about a backup window.

| Property | Type | Description |
| --- | --- | --- |
| BackupWindow | Bool[] | Array of booleans.  If True, the allowed backup hour is created. If False, the prohibited backup hours is created. |
| MinuteOffset | Int | Current minute offset from the UTC time. |

Related Commands

* [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md)
* [Set-VBOJobSchedulePolicy](set-vbojobschedulepolicy.md)
* [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md)
* [Set-VBOBackupWindowSettings](set-vbobackupwindowsettings.md)
* [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md)
* [Set-VBOCopyJobSchedulePolicy](set-vbocopyjobschedulepolicy.md)


