---
title: "Set-VBOBackupWindowSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbobackupwindowsettings.html"
last_updated: "1/6/2026"
product_version: "8.3.0.2201"
---

# Set-VBOBackupWindowSettings


Short Description

Modifies the backup window settings.

Syntax

|  |
| --- |
| Set-VBOBackupWindowSettings -Settings <VBOBackupWindowSettings> -FromDay <DayOfWeek> -FromHour <Int32> -ToDay <DayOfWeek> -ToHour <Int32> [-Enabled] [<CommonParameters>] |

Detailed Description

This cmdlet modifies the backup window settings. You can use a backup window object when creating or modifying backup job and backup copy job schedule settings. For more information on how to create backup job and backup copy job schedule settings, see the [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md) and [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md) cmdlets.

To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Settings | Specifies a backup window that you want to modify. | Accepts the [VBOBackupWindowSettings](vbobackupwindowsettings.md) object.  To create this object, run the [New-VBOBackupWindowSettings](new-vbobackupwindowsettings.md) cmdlet. | True | Named | True (ByValue, ByPropertyName) |
| FromDay | Specifies the day of the week on which the backup window opens. | DayOfWeek | True | Named | False |
| FromHour | Specifies the hour on which the backup window opens. | Int32 | True | Named | False |
| ToDay | Specifies the day of the week on which the backup window ends. | DayOfWeek | True | Named | False |
| ToHour | Specifies the hour on which the backup window ends. | Int32 | True | Named | False |
| Enabled | Defines that the cmdlet will create a backup window with allowed backup hours.  Default: False  If this parameter is set to false, the cmdlet will create a backup window with prohibited backup hours. | SwitchParameter | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Adding Allowed Backup Hours to Backup Window

|  |  |
| --- | --- |
| This example shows how to add allowed backup hours to the backup window of the existing job.  |  | | --- | | $job = Get-VBOJob -Name "ABC: Sales"  $schedule = $job.SchedulePolicy  $awindow = $schedule.BackupWindowSettings  $newawindow = Set-VBOBackupWindowSettings -Settings $awindow -FromDay Saturday -FromHour 8 -ToDay Saturday -ToHour 17 -Enabled:$true  $newschedule = Set-VBOJobSchedulePolicy -Policy $schedule -BackupWindowEnabled -BackupWindowSettings $newawindow  Set-VBOJob -Job $job -SchedulePolicy $newschedule |  Perform the following steps:   1. Get the backup window of the existing job:  1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get a backup job whose backup window settings you want to modify. Save the result to the $job variable. 2. Get the job schedule settings. Use the SchedulePolicy property of the job object saved to the $job variable. Save the result to the $schedule variable. 3. Get the backup window. Use the BackupWindowSettings property of the schedule policy object saved to the $schedule variable. Save the result to the $awindow variable.  1. Run the Set-VBOBackupWindowSettings cmdlet with the $awindow variable to modify the backup window settings. Save the result to the $newawindow variable. 2. Apply the new backup window settings to the backup job schedule:  1. Run the [Set-VBOJobSchedulePolicy](set-vbojobschedulepolicy.md) cmdlet with the $schedule and $newawindow variables to modify the job schedule settings. Save the result to the $newschedule variable. 2. Run the [Set-VBOJob](set-vbojob.md) cmdlet with the $job and $newschedule variables. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Adding Prohibited Backup Hours to Backup Window

|  |  |
| --- | --- |
| This example shows how to add prohibited backup hours to the backup window of the existing job.  |  | | --- | | $job = Get-VBOJob -Name "ABC: Sales"  $schedule = $job.SchedulePolicy  $pwindow = $schedule.BackupWindowSettings  $newpwindow = Set-VBOBackupWindowSettings -Settings $pwindow -FromDay Monday -FromHour 12 -ToDay Monday -ToHour 13 -Enabled:$false  $newschedule = Set-VBOJobSchedulePolicy -Policy $schedule -BackupWindowEnabled -BackupWindowSettings $newpwindow  Set-VBOJob -Job $job -SchedulePolicy $newschedule |  Perform the following steps:   1. Get the backup window of the existing job:  1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get a backup job whose backup window settings you want to modify. Save the result to the $job variable. 2. Get the job schedule settings. Use the SchedulePolicy property of the job object saved to the $job variable. Save the result to the $schedule variable. 3. Get the backup window. Use the BackupWindowSettings property of the schedule policy object saved to the $schedule variable. Save the result to the $pwindow variable.  1. Run the Set-VBOBackupWindowSettings cmdlet with the $pwindow variable to modify the backup window settings. Save the result to the $newpwindow variable. 2. Apply the new backup window settings to the backup job schedule:  1. Run the [Set-VBOJobSchedulePolicy](set-vbojobschedulepolicy.md) cmdlet with the $schedule and $newpwindow variables to modify the job schedule settings. Save the result to the $newschedule variable. 2. Run the [Set-VBOJob](set-vbojob.md) cmdlet with the $job and $newschedule variables. |

Related Commands

* [Set-VBOJobSchedulePolicy](set-vbojobschedulepolicy.md)
* [Get-VBOJob](get-vbojob.md)
* [Set-VBOJob](set-vbojob.md)


