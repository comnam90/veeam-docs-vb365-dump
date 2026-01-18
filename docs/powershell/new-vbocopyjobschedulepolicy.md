---
title: "New-VBOCopyJobSchedulePolicy"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vbocopyjobschedulepolicy.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# New-VBOCopyJobSchedulePolicy


Short Description

Creates a backup copy job schedule.

Syntax

This cmdlet provides parameter sets that allow you to:

* Run a backup copy job immediately.

|  |
| --- |
| New-VBOCopyJobSchedulePolicy [-Type <VBOCopyJobFrequencyType>] [-BackupWindowSettings <VBOBackupWindowSettings>] [<CommonParameters>] |

* Create periodical job schedule.

|  |
| --- |
| New-VBOCopyJobSchedulePolicy [-Type <VBOCopyJobFrequencyType>] [-PeriodicallyEvery <VBOPeriodicInterval>] [-BackupWindowSettings <VBOBackupWindowSettings>] [<CommonParameters>] |

* Create daily job schedule.

|  |
| --- |
| New-VBOCopyJobSchedulePolicy [-Type <VBOCopyJobFrequencyType>] [-DailyTime <TimeSpan>] [-DailyType <VBODailyType>] [-BackupWindowSettings <VBOBackupWindowSettings>] [<CommonParameters>] |

Detailed Description

This cmdlet creates a backup copy job schedule.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Type | Specifies a type of the backup copy job schedule:   * Immediate: runs the backup copy job right after the latest restore point appears in the source backup repository.   During the first run of the backup copy job, Veeam Backup for Microsoft 365 copies the latest restore point created by the source backup job (backup job for which you create a backup copy job). During next runs — each subsequent restore point.   * Daily: runs the backup copy job on specific days at the specified hours. * Periodically: runs the backup copy job repeatedly throughout a day with a specific time interval. | VBOCopyJobFrequencyType | False | Named | False |
| BackupWindowSettings | Specifies the backup window within which the backup copy job must be completed. | Accepts the [VBOBackupWindowSettings](vbobackupwindowsettings.md) object.  To create this object, run the [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md) cmdlet. | False | Named | False |
| PeriodicallyEvery | Specifies the time interval between the job runs:   * Minutes5 * Minutes10 * Minutes15 * Minutes30 * Hours1 * Hours2 * Hours4 * Hours8  * Hours12   Default: Minutes5 | VBOPeriodicInterval | False | Named | False |
| DailyTime | Specifies the time to start the backup copy job.  Default: 15:00:00 | TimeSpan | False | Named | False |
| DailyType | Specifies the days when the backup copy job will run:   * Everyday * Weekends * Workdays * Monday * Tuesday * Wednesday * Thursday * Friday * Saturday * Sunday   Default: Everyday | VBODailyType | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOCopyJobSchedulePolicy](vbocopyjobschedulepolicy.md) object that contains the backup copy job schedule settings.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Creating Daily Schedule for Backup Copy Job

|  |  |
| --- | --- |
| This example shows how to configure a daily job schedule for a backup copy job. A backup copy job schedule will have the following settings:   * A backup copy job will run everyday at 10 AM. * A backup copy job will stop if its processing exceeds the allowed backup window.   |  | | --- | | $copyjob = Get-VBOCopyJob -Id 8b6b539e-15cc-4ed6-bd1d-b8c7c918f413  $bwindow = New-VBOBackupWindowSettings -FromDay Monday -FromHour 8 -ToDay Sunday -ToHour 17 -Enabled:$true  $daily = New-VBOCopyJobSchedulePolicy -Type Daily -DailyType Everyday -DailyTime 10:00:00 -BackupWindowSettings $bwindow  Set-VBOCopyJob -Job $copyjob -SchedulePolicy $daily |  Perform the following steps:   1. Run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet to get a backup copy job whose schedule settings you want to configure. Specify the Id parameter value. Save the result to the $copyjob variable. 2. Run the [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md) cmdlet to create a backup window within which the backup copy job must be completed. Save the result to the $bwindow variable. 3. Run the New-VBOCopyJobSchedulePolicy cmdlet with the $bwindow variable to set the job schedule. Save the result to the $daily variable. 4. Run the [Set-VBOCopyJob](set-vbocopyjob.md) cmdlet with the $copyjob and $daily variables to apply the schedule settings to the backup copy job. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Creating Periodical Schedule for Backup Copy Job

|  |  |
| --- | --- |
| This example shows how to configure a periodical job schedule for a backup copy job. A backup copy job will run every 8 hours.  |  | | --- | | $copyjob = Get-VBOCopyJob -Id 8b6b539e-15cc-4ed6-bd1d-b8c7c918f413  $every8hours = New-VBOCopyJobSchedulePolicy -Type Periodically -PeriodicallyEvery Hours8  Set-VBOCopyJob -Job $copyjob -SchedulePolicy $every8hours |  Perform the following steps:   1. Run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet to get a backup copy job whose schedule settings you want to configure. Specify the Id parameter value. Save the result to the $copyjob variable. 2. Run the New-VBOCopyJobSchedulePolicy cmdlet to set the job schedule. Save the result to the $every8hours variable. 3. Run the [Set-VBOCopyJob](set-vbocopyjob.md) cmdlet with the $copyjob and $every8hours variables to apply the schedule settings to the backup copy job. |

Related Commands

* [Get-VBOCopyJob](get-vbocopyjob.md)
* [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md)
* [Set-VBOCopyJob](set-vbocopyjob.md)


