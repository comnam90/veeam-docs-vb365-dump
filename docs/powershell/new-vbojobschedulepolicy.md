---
title: "New-VBOJobSchedulePolicy"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vbojobschedulepolicy.html"
last_updated: "1/6/2026"
product_version: "8.3.0.2201"
---

# New-VBOJobSchedulePolicy


Short Description

Creates a backup job schedule.

Syntax

This cmdlet provides parameter sets that allow you to:

* Create daily job schedule.

|  |
| --- |
| New-VBOJobSchedulePolicy [-EnableSchedule] [-Type <VBOJobFrequencyType>] [-DailyTime <TimeSpan>] [-DailyType <VBODailyType>] [-BackupWindowSettings <VBOBackupWindowSettings>] [-RetryEnabled] [-RetryNumber <Int32>] [-RetryWaitInterval <Int32>] [<CommonParameters>] |

* Create periodical job schedule.

|  |
| --- |
| New-VBOJobSchedulePolicy [-EnableSchedule] [-Type <VBOJobFrequencyType>] [-PeriodicallyEvery <VBOPeriodicInterval>] [-BackupWindowSettings <VBOBackupWindowSettings>] [-PeriodicallyWindowSettings <VBOBackupWindowSettings>] [-PeriodicallyOffsetMinutes <Int32>] [-RetryEnabled] [-RetryNumber <Int32>] [-RetryWaitInterval <Int32>] [<CommonParameters>] |

Detailed Description

This cmdlet creates a backup job schedule.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| EnableSchedule | Defines that the backup job will be configured to follow this schedule. If you set this parameter to the EnableSchedule:$false value, the backup job will not be scheduled.  Default: True | SwitchParameter | False | Named | False |
| Type | Specifies a type of the backup job schedule:   * Daily: runs the backup job on specific days at the specified hours. * Periodically: runs the backup job repeatedly throughout a day with a specific time interval. | VBOJobFrequencyType | False | Named | False |
| DailyTime | Specifies the time to start the backup job.  Default: 15:00:00 | TimeSpan | False | Named | False |
| DailyType | Specifies the days when the backup job will run:   * Everyday * Weekends * Workdays * Monday * Tuesday * Wednesday * Thursday * Friday * Saturday * Sunday   Default: Everyday | VBODailyType | False | Named | False |
| BackupWindowSettings | Specifies the backup window within which the backup job must be completed. | Accepts the [VBOBackupWindowSettings](vbobackupwindowsettings.md) object.  To create this object, run the [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md) cmdlet. | False | Named | False |
| RetryEnabled | Defines that Veeam Backup for Microsoft 365 will attempt to run a backup job again if the job fails for some reason.  Default: False | SwitchParameter | False | Named | False |
| RetryNumber | Specifies the number of attempts to run the backup job.  Permitted values: 1–777.  Default: 3 | Int32 | False | Named | False |
| RetryWaitInterval | Specifies the time intervals between the job retry attempts in minutes.  Permitted values: 1–999.  Default: 10 | Int32 | False | Named | False |
| PeriodicallyEvery | Specifies the time interval between the job runs:   * Minutes5 * Minutes10 * Minutes15 * Minutes30 * Hours1 * Hours2 * Hours4 * Hours8 * Hours12   Default: Minutes5 | VBOPeriodicInterval | False | Named | False |
| PeriodicallyWindowSettings | Specifies the backup window within which the backup job will run periodically. | Accepts the [VBOBackupWindowSettings](vbobackupwindowsettings.md) object.  To create this object, run the [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md) cmdlet. | False | Named | False |
| PeriodicallyOffsetMinutes | Specifies the offset within an hour in minutes after which the job must start according to the periodic schedule.  Permitted values: 0–59.  Default: 0 | Int32 | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOJobSchedulePolicy](vbojobschedulepolicy.md) object that contains the backup job schedule settings.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Creating Daily Schedule for Backup Job

|  |  |
| --- | --- |
| This example shows how to configure a daily job schedule for a backup job. A job schedule will have the following settings:   * A backup job will run everyday at 8 AM. * A backup job will stop if its processing exceeds the allowed backup window.   |  | | --- | | $job = Get-VBOJob -Name "ABC: Sales"  $bwindow = New-VBOBackupWindowSettings -FromDay Monday -FromHour 8 -ToDay Sunday -ToHour 17 -Enabled:$true  $daily = New-VBOJobSchedulePolicy -Type Daily -DailyType Everyday -DailyTime 08:00:00 -BackupWindowSettings $bwindow  Set-VBOJob -Job $job -SchedulePolicy $daily |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get a backup job whose schedule settings you want to configure. Save the result to the $job variable. 2. Run the [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md) cmdlet to create a backup window within which the backup job must be completed. Save the result to the $bwindow variable. 3. Run the New-VBOJobSchedulePolicy cmdlet with the $bwindow variable to set the job schedule. Save the result to the $daily variable. 4. Run the [Set-VBOJob](set-vbojob.md) cmdlet with the $job and $daily variables to apply new schedule settings to the backup job. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Creating Periodical Schedule for Backup Job

|  |  |
| --- | --- |
| This example shows how to configure a periodical job schedule for a backup job. A job schedule will have the following settings:   * A backup job will run every 4 hours. * Veeam Backup for Microsoft 365 will not restart a backup job if it fails.   |  | | --- | | $job = Get-VBOJob -Name "ABC: Sales"  $every4noretry = New-VBOJobSchedulePolicy -Type Periodically -PeriodicallyEvery Hours4 -RetryEnabled:$false  Set-VBOJob -Job $job -SchedulePolicy $every4noretry |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get a backup job. Save the result to the $job variable. 2. Run the New-VBOJobSchedulePolicy cmdlet to set the job schedule. Save the result to the $every4noretry variable. 3. Run the [Set-VBOJob](set-vbojob.md) cmdlet with the $job and $every4noretry variables. |

Related Commands

* [Get-VBOJob](get-vbojob.md)
* [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md)
* [Set-VBOJob](set-vbojob.md)


