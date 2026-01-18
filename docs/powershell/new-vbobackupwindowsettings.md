---
title: "New-VBOBackupWindowSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vbobackupwindowsettings.html"
last_updated: "1/6/2026"
product_version: "8.3.0.2201"
---

# New-VBOBackupWindowSettings


Short Description

Creates a backup window.

Syntax

|  |
| --- |
| New-VBOBackupWindowSettings -FromDay <DayOfWeek> -FromHour <Int32> -ToDay <DayOfWeek> -ToHour <Int32> [-Enabled] [<CommonParameters>] |

Detailed Description

This cmdlet creates a backup window for a backup job or a backup copy job. The backup window sets a time period within which the job must be completed.

You can use a backup window object when creating or modifying backup or backup copy job schedule settings.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| FromDay | Specifies the day of the week on which the backup window opens. | DayOfWeek | True | Named | False |
| FromHour | Specifies the hour on which the backup window opens. | Int32 | True | Named | False |
| ToDay | Specifies the day of the week on which the backup window ends. | DayOfWeek | True | Named | False |
| ToHour | Specifies the hour on which the backup window ends. | Int32 | True | Named | False |
| Enabled | Defines that the cmdlet will create a backup window with allowed backup hours.  Default: False  If this parameter is set to false, the cmdlet will create a backup window with prohibited backup hours. | SwitchParameter | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOBackupWindowSettings](vbobackupwindowsettings.md) object that contains the backup window settings.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Creating Backup Window with Allowed Hours

|  |  |
| --- | --- |
| This example shows how to create a backup window with allowed backup hours from 8 AM on Monday to 5 PM on Saturday and add it to the new job schedule.  |  | | --- | | $awindow = New-VBOBackupWindowSettings -FromDay Monday -FromHour 8 -ToDay Saturday -ToHour 17 -Enabled:$true  $daily = New-VBOJobSchedulePolicy -Type Daily -DailyType Everyday -DailyTime 08:00:00 -BackupWindowSettings $awindow  $job = Get-VBOJob -Name "ABC: Sales"  Set-VBOJob -Job $job -SchedulePolicy $daily |  Perform the following steps:   1. Run the New-VBOBackupWindowSettings cmdlet to create a backup window within which the backup job is allowed to run. Save the result to the $awindow variable. 2. Run the [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md) cmdlet with the $awindow variable to create the job schedule. Save the result to the $daily variable. 3. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get a backup job whose schedule settings you want to modify. Save the result to the $job variable. 4. Run the [Set-VBOJob](set-vbojob.md) cmdlet with the $job and $daily variables to apply new schedule settings to the backup job. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Creating Backup Window with Prohibited Hours

|  |  |
| --- | --- |
| This example shows how to create a backup window with prohibited backup hours from 8 AM to 5 PM on Monday and add it to the new job schedule.  |  | | --- | | $pwindow = New-VBOBackupWindowSettings -FromDay Monday -FromHour 8 -ToDay Monday -ToHour 17 -Enabled:$false  $daily = New-VBOJobSchedulePolicy -Type Daily -DailyType Everyday -DailyTime 08:00:00 -BackupWindowSettings $pwindow  $job = Get-VBOJob -Name "ABC: Sales"  Set-VBOJob -Job $job -SchedulePolicy $daily |  Perform the following steps:   1. Run the New-VBOBackupWindowSettings cmdlet to create a backup window within which the backup job is not allowed to run. Save the result to the $pwindow variable. 2. Run the [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md) cmdlet with the $pwindow variable to create the job schedule. Save the result to the $daily variable. 3. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get a backup job whose schedule settings you want to modify. Save the result to the $job variable. 4. Run the [Set-VBOJob](set-vbojob.md) cmdlet with the $job and $daily variables to apply new schedule settings to the backup job. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Adding New Backup Window to Existing Backup Job Schedule

|  |  |
| --- | --- |
| This example shows how to create a backup window and add it to the existing job schedule.  |  | | --- | | $job = Get-VBOJob -Name "ABC: Sales"  $schedule = $job.schedulepolicy  $bw = New-VBOBackupWindowSettings -FromDay Friday -FromHour 2 -ToDay Monday -ToHour 3 -Enabled:$true  $newschedule = Set-VBOJobSchedulePolicy -Policy $schedule -BackupWindowEnabled -BackupWindowSettings $bw  Set-VBOJob -Job $job -SchedulePolicy $newschedule |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get a backup job whose schedule settings you want to modify. Save the result to the $job variable. 2. Get the job schedule settings. Use the SchedulePolicy property of the job object saved to the $job variable. Save the result to the $schedule variable. 3. Run the New-VBOBackupWindowSettings cmdlet to create a backup window. Save the result to the $bw variable. 4. Run the [Set-VBOJobSchedulePolicy](set-vbojobschedulepolicy.md) cmdlet with the $bw variable to modify the job schedule settings. Save the result to the $newschedule variable. 5. Run the [Set-VBOJob](set-vbojob.md) cmdlet with the $job and $newschedule variables to apply new schedule settings to the backup job. |

Related Commands

* [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md)
* [Set-VBOJobSchedulePolicy](set-vbojobschedulepolicy.md)
* [Get-VBOJob](get-vbojob.md)
* [Set-VBOJob](set-vbojob.md)


