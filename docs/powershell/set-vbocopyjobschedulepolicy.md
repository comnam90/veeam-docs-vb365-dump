---
title: "set-vbocopyjobschedulepolicy"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbocopyjobschedulepolicy.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies the backup copy job schedule settings.

Syntax

This cmdlet provides parameter sets that allow you to:

* Change the schedule type to Immediate.

|  |
| --- |
| Set-VBOCopyJobSchedulePolicy -Policy <VBOCopyJobSchedulePolicy> [-Type <VBOCopyJobFrequencyType>] [-BackupWindowSettings <VBOBackupWindowSettings>] [-EnableBackupWindow] [<CommonParameters>] |

* Change the schedule type to Periodically.

|  |
| --- |
| Set-VBOCopyJobSchedulePolicy -Policy <VBOCopyJobSchedulePolicy> [-Type <VBOCopyJobFrequencyType>] [-PeriodicallyEvery <VBOPeriodicInterval>] [-BackupWindowSettings <VBOBackupWindowSettings>] [-EnableBackupWindow] [<CommonParameters>] |

* Change the schedule type to Daily.

|  |
| --- |
| Set-VBOCopyJobSchedulePolicy -Policy <VBOCopyJobSchedulePolicy> [-Type <VBOCopyJobFrequencyType>] [-DailyTime <TimeSpan>] [-DailyType <VBODailyType>] [-BackupWindowSettings <VBOBackupWindowSettings>] [-EnableBackupWindow] [<CommonParameters>] |

Detailed Description

This cmdlet modifies the backup copy job schedule settings. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Policy | Specifies the backup copy job schedule whose settings you want to modify. | Accepts the VBOCopyJobSchedulePolicy object.  To create this object, run the [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md) cmdlet. | True | Named | True (ByValue) |
| Type | Specifies a type of the backup copy job schedule:   * Immediate: runs the backup copy job right after the latest restore point appears in the source backup repository.   During the first run of the backup copy job, Veeam Backup for Microsoft 365 copies the latest restore point created by the source backup job (backup job for which you create a backup copy job). During next runs — each subsequent restore point.   * Daily: runs the backup copy job on specific days at the specified hours. * Periodically: runs the backup copy job repeatedly throughout a day with a specific time interval. | VBOCopyJobFrequencyType | False | Named | False |
| BackupWindowSettings | Specifies the backup window within which the backup copy job must be completed. | Accepts the VBOBackupWindowSettings object.  To create this object, run the [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md) cmdlet. | False | Named | False |
| EnableBackupWindow | Defines that the job run will be terminated if it exceeds the allowed backup window.  Default: False | SwitchParameter | False | Named | False |
| PeriodicallyEvery | Specifies the time interval between the job runs:   * Minutes5 * Minutes10 * Minutes15 * Minutes30 * Hours1 * Hours2 * Hours4 * Hours8  * Hours12 | VBOPeriodicInterval | False | Named | False |
| DailyTime | Specifies the time to start the backup copy job. | TimeSpan | False | Named | False |
| DailyType | Specifies the days when the backup copy job will run:   * Everyday * Weekends * Workdays * Monday * Tuesday * Wednesday * Thursday * Friday * Saturday * Sunday | VBODailyType | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOCopyJobSchedulePolicy object that contains the backup copy job schedule settings.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Changing Backup Copy Job Schedule Type to Immediate

|  |  |
| --- | --- |
| This example shows how to modify the settings of a backup copy job schedule:   * Veeam Backup for Microsoft 365 will now run a backup copy job immediately. * A backup copy job will now stop if its processing exceeds the allowed backup window.   |  | | --- | | $copyjob = Get-VBOCopyJob -Id 8b6b539e-15cc-4ed6-bd1d-b8c7c918f413  $schedule = $copyjob.schedulepolicy  $bwindow = New-VBOBackupWindowSettings -FromDay Monday -FromHour 8 -ToDay Sunday -ToHour 17 -Enabled:$true  Set-VBOCopyJobSchedulePolicy -Policy $schedule -Type Immediate -EnableBackupWindow -BackupWindowSettings $bwindow  Set-VBOCopyJob -Job $copyjob -SchedulePolicy $schedule |  Perform the following steps:   1. Run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet to get a backup copy job whose schedule settings you want to modify. Specify the Id parameter value. Save the result to the $copyjob variable. 2. Get the job schedule settings that you want to modify. Use the SchedulePolicy property of the VBOCopyJob object saved to the $copyjob variable. Save the result to the $schedule variable. 3. Run the [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md) cmdlet to create a backup window within which the backup copy job is allowed to run. Save the result to the $bwindow variable. 4. Run the Set-VBOCopyJobSchedulePolicy cmdlet with the $schedule and $bwindow variables to modify the backup copy job schedule settings. 5. Run the [Set-VBOCopyJob](set-vbocopyjob.md) cmdlet with the $copyjob and $schedule variables to apply the schedule with the new settings to the backup copy job. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Changing Backup Copy Job Schedule Type from Daily to Periodically

|  |  |
| --- | --- |
| This example shows how to change the type of a backup copy job schedule from Daily to Periodically. A backup copy job per this schedule will now run every 4 hours.  |  | | --- | | $copyjob = Get-VBOCopyJob -Id 8b6b539e-15cc-4ed6-bd1d-b8c7c918f413  $pschedule = $copyjob.schedulepolicy  Set-VBOCopyJobSchedulePolicy -Policy $pschedule -Type Periodically -PeriodicallyEvery Hours4  Set-VBOCopyJob -Job $copyjob -SchedulePolicy $pschedule |  Perform the following steps:   1. Run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet to get a backup copy job whose schedule settings you want to modify. Specify the Id parameter value. Save the result to the $copyjob variable. 2. Get the job schedule settings that you want to modify. Use the SchedulePolicy property of the VBOCopyJob object saved to the $copyjob variable. Save the result to the $pschedule variable. 3. Run the Set-VBOCopyJobSchedulePolicy cmdlet with the $pschedule variable to modify the backup copy job schedule settings. 4. Run the [Set-VBOCopyJob](set-vbocopyjob.md) cmdlet with the $copyjob and $pschedule variables to apply the schedule with the new settings to the backup copy job. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Changing Backup Copy Job Schedule Type from Periodically to Daily

|  |  |
| --- | --- |
| This example shows how to change the type of a backup copy job schedule from Periodically to Daily. A backup copy job per this schedule will now run on workdays at 10:00:00.  |  | | --- | | $copyjob = Get-VBOCopyJob -Id 8b6b539e-15cc-4ed6-bd1d-b8c7c918f413  $dschedule = $copyjob.schedulepolicy  Set-VBOCopyJobSchedulePolicy -Policy $dschedule -Type Daily -DailyType Workdays -DailyTime 10:00:00  Set-VBOCopyJob -Job $copyjob -SchedulePolicy $dschedule |  Perform the following steps:   1. Run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet to get a backup copy job whose schedule settings you want to modify. Specify the Id parameter value. Save the result to the $copyjob variable. 2. Get the job schedule settings that you want to modify. Use the SchedulePolicy property of the VBOCopyJob object saved to the $copyjob variable. Save the result to the $dschedule variable. 3. Run the Set-VBOCopyJobSchedulePolicy cmdlet with the $dschedule variable to modify the backup copy job schedule settings. 4. Run the [Set-VBOCopyJob](set-vbocopyjob.md) cmdlet with the $copyjob and $dschedule variablesto apply the schedule with the new settings to the backup copy job. |

Related Commands

* [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md)
* [Get-VBOCopyJob](get-vbocopyjob.md)
* [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md)
* [Set-VBOCopyJob](set-vbocopyjob.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
