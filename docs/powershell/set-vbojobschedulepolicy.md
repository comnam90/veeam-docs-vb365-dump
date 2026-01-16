---
title: "set-vbojobschedulepolicy"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbojobschedulepolicy.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies the backup job schedule settings.

Syntax

This cmdlet provides parameter sets that allow you to:

* Change the schedule type to Periodically.

|  |
| --- |
| Set-VBOJobSchedulePolicy -Policy <VBOJobSchedulePolicy> [-Type <VBOJobFrequencyType>] [-PeriodicallyEvery <VBOPeriodicInterval>] [-BackupWindowEnabled] [-PeriodicallyWindowSettings <VBOBackupWindowSettings>] [-PeriodicallyOffsetMinutes <Int32>] [-BackupWindowSettings <VBOBackupWindowSettings>] [-RetryEnabled] [-RetryNumber <Int32>] [-RetryWaitInterval <Int32>] [-EnableSchedule] [<CommonParameters>] |

* Change the schedule type to Daily.

|  |
| --- |
| Set-VBOJobSchedulePolicy -Policy <VBOJobSchedulePolicy> [-Type <VBOJobFrequencyType>] [-DailyTime <TimeSpan>] [-DailyType <VBODailyType>] [-BackupWindowEnabled] [-BackupWindowSettings <VBOBackupWindowSettings>] [-RetryEnabled] [-RetryNumber <Int32>] [-RetryWaitInterval <Int32>] [-EnableSchedule] [<CommonParameters>] |

Detailed Description

This cmdlet modifies the backup job schedule settings. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Policy | Specifies the backup job schedule whose settings you want to modify. | Accepts the VBOJobSchedulePolicy object.  To create this object, run the [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md) cmdlet. | True | Named | True (ByValue) |
| Type | Specifies a type of the backup job schedule:   * Daily: runs the backup job on specific days at the specified hours. * Periodically: runs the backup job repeatedly throughout a day with a specific time interval. | VBOJobFrequencyType | False | Named | False |
| PeriodicallyEvery | Specifies the time interval between the job runs:   * Minutes5 * Minutes10 * Minutes15 * Minutes30 * Hours1 * Hours2 * Hours4 * Hours8 * Hours12 | VBOPeriodicInterval | False | Named | False |
| BackupWindowEnabled | Defines that the job run will be terminated if it exceeds the allowed backup window.  Default: False | SwitchParameter | False | Named | False |
| PeriodicallyWindowSettings | Specifies the backup window within which the backup job will run periodically. | Accepts the VBOBackupWindowSettings object.  To create this object, run the [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md) cmdlet. | False | Named | False |
| PeriodicallyOffsetMinutes | Specifies the offset within an hour in minutes after which the job must start according to the periodic schedule.  Permitted values: 0–59.  Default: 0 | Int32 | False | Named | False |
| BackupWindowSettings | Specifies the backup window within which the backup job must be completed. | Accepts the VBOBackupWindowSettings object.  To create this object, run the [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md) cmdlet. | False | Named | False |
| RetryEnabled | Defines that Veeam Backup for Microsoft 365 will attempt to run a backup job again if the job fails for some reason.  Default: False | SwitchParameter | False | Named | False |
| RetryNumber | Specifies the number of attempts to run the backup job.  Permitted values: 1–777.  Default: 3 | Int32 | False | Named | False |
| RetryWaitInterval | Specifies the time intervals between the job retry attempts in minutes.  Permitted values: 1–999.  Default: 10 | Int32 | False | Named | False |
| EnableSchedule | Defines that the backup job will be configured to follow this schedule. If you set this parameter to the EnableSchedule:$false value, the backup job will not be scheduled.  Default: True | SwitchParameter | False | Named | False |
| DailyTime | Specifies the time to start the backup job. | TimeSpan | False | Named | False |
| DailyType | Specifies the days when the backup job will run:   * Everyday * Weekends * Workdays * Monday * Tuesday * Wednesday * Thursday * Friday * Saturday * Sunday | VBODailyType | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOJobSchedulePolicy object that contains the backup job schedule settings.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Backup Job Schedule Settings

|  |  |
| --- | --- |
| This example shows how to modify the settings of a backup job schedule:   * Veeam Backup for Microsoft 365 will now restart a backup job if it fails. * Veeam Backup for Microsoft 365 will now perform 4 attempts to retry a failed job with 1 minute interval. * A backup job will now stop if its processing exceeds the allowed backup window.   |  | | --- | | $job = Get-VBOJob -Name "ABC: Sales"  $schedule = $job.schedulepolicy  $bwindow = New-VBOBackupWindowSettings -FromDay Monday -FromHour 8 -ToDay Sunday -ToHour 17 -Enabled:$true  Set-VBOJobSchedulePolicy -Policy $schedule -BackupWindowEnabled -BackupWindowSettings $bwindow -RetryEnabled -RetryNumber 4 -RetryWaitInterval 1  Set-VBOJob -Job $job -SchedulePolicy $schedule |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get a backup job whose schedule settings you want to modify. Save the result to the $job variable. 2. Get the job schedule settings that you want to modify. Use the SchedulePolicy property of the job object saved to the $job variable. Save the result to the $schedule variable. 3. Run the [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md) cmdlet to create a backup window within which the backup job is allowed to run. Save the result to the $bwindow variable. 4. Run the Set-VBOJobSchedulePolicy cmdlet with the $schedule and $bwindow variables to modify the job schedule settings. 5. Run the [Set-VBOJob](set-vbojob.md) cmdlet with the $job and $schedule variables to apply the schedule with the new settings to a backup job. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Changing Backup Job Schedule Type from Daily to Periodically

|  |  |
| --- | --- |
| This example shows how to change the type of a job schedule from Daily to Periodically. A backup job per this schedule will now run every 2 hours.  |  | | --- | | $job = Get-VBOJob -Name "ABC: Sales"  $pschedule = $job.schedulepolicy  Set-VBOJobSchedulePolicy -Policy $pschedule -Type Periodically -PeriodicallyEvery Hours2  Set-VBOJob -Job $job -SchedulePolicy $pschedule |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get a backup job whose schedule settings you want to modify. Save the result to the $job variable. 2. Get the job schedule settings you want to modify. Use the SchedulePolicy property of the job object saved to the $job variable. Save the result to the $pschedule variable. 3. Run the Set-VBOJobSchedulePolicy cmdlet with the $pschedule variable to modify the job schedule settings. 4. Run the [Set-VBOJob](set-vbojob.md) cmdlet with the $job and $pschedule variables to apply the schedule with the new settings to a backup job. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Changing Backup Job Schedule Type from Periodically to Daily

|  |  |
| --- | --- |
| This example shows how to change the type of a job schedule from Periodically to Daily. A backup job per this schedule will now run on workdays at 08:00:00.  |  | | --- | | $job = Get-VBOJob -Name "ABC: Sales"  $dschedule = $job.schedulepolicy  Set-VBOJobSchedulePolicy -Policy $dschedule -Type Daily -DailyType Workdays -DailyTime 08:00:00  Set-VBOJob -Job $job -SchedulePolicy $dschedule |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get a backup job whose schedule settings you want to modify. Save the result to the $job variable. 2. Get the job schedule settings you want to modify. Use the SchedulePolicy property of the job object saved to the $job variable. Save the result to the $dschedule variable. 3. Run the Set-VBOJobSchedulePolicy cmdlet with the $dschedule variable to modify the job schedule settings. 4. Run the [Set-VBOJob](set-vbojob.md) cmdlet with the $job and $dschedule variables to apply the schedule with the new settings to a backup job. |

Related Commands

* [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md)
* [Get-VBOJob](get-vbojob.md)
* [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md)
* [Set-VBOJob](set-vbojob.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
