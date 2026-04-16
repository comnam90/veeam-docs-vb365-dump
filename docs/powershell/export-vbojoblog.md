---
title: "Export-VBOJobLog"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/export-vbojoblog.html"
last_updated: "3/11/2026"
product_version: "8.4.0.1457"
---

# Export-VBOJobLog


Short Description

Exports the Veeam Backup for Microsoft 365 job log files.

Syntax

This cmdlet provides parameter sets that allow you to:

* Export all collected logs.

|  |
| --- |
| Export-VBOJobLog [-JobIds] <Guid[]> [-All] -TargetPath <String> [<CommonParameters>] |

* Export logs for the specified time period.

|  |
| --- |
| Export-VBOJobLog [-JobIds] <Guid[]> [-From <DateTime>] [-To <DateTime>] -TargetPath <String> [<CommonParameters>] |

* Export logs collected for the specified number of days.

|  |
| --- |
| Export-VBOJobLog [-JobIds] <Guid[]> -DayPeriod <Int32> -TargetPath <String> [<CommonParameters>] |

Detailed Description

This cmdlet exports log files collected for the specified Veeam Backup for Microsoft 365 jobs.

|  |
| --- |
| Note |
| If a job or a Microsoft organization is renamed, logs created before the renaming are not exported. |

To export log files collected for the Veeam Backup for Microsoft 365 server components, run the [Export-VBOLog](export-vbolog.md) cmdlet.

Parameters

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| JobIds | Specifies an array of job IDs. The cmdlet will export logs for jobs with the specified IDs. | Guid[] | True | 0 | False |
| All | Defines that the cmdlet will export logs for all time. You cannot use the From, To and DayPeriod parameters if this parameter is used.  Default: False | SwitchParameter | True | Named | False |
| TargetPath | Specifies a target path for the log export. The cmdlet will export log files to this location. | String | True | Named | False |
| From | Specifies date and time, starting from which this cmdlet will export the logs. If this parameter is used, you must use the To parameter and you cannot use the All and DayPeriod parameters. You must enter date and time in a DateTime format. | DateTime | False | Named | False |
| To | Specifies the date and time, until which this cmdlet will export the logs. If this parameter is used, you must use the From parameter and you cannot use the All and DayPeriod parameters. You must enter date and time in a DateTime format. | DateTime | False | Named | False |
| DayPeriod | Specifies the number of last N days. The cmdlet will export logs for these days.  Permitted values: 1–999.  Note: You cannot use the All, From and To parameters if this parameter is used. | Int32 | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Exporting All Logs Collected for Veeam Backup for Microsoft 365 Job

|  |  |
| --- | --- |
| This example shows how to export all logs collected for a job. The cmdlet will export logs with the following settings:   * Logs will be exported for a job with the ID a19840ea-9cf5-413d-af29-57ecad85be9e.  * The cmdlet will export logs to the C:\Veeam\Office365\Logs folder.   |  | | --- | | Get-VBOJobSession  Export-VBOJobLog -JobIds a19840ea-9cf5-413d-af29-57ecad85be9e -TargetPath "C:\Veeam\Office365\Logs" -All |  Perform the following steps:   1. Run the [Get-VBOJobSession](get-vbojobsession.md) cmdlet. The cmdlet will return details of all Veeam Backup for Microsoft 365 jobs. Copy the JobId value from the cmdlet output. 2. Run the Export-VBOJobLog cmdlet. Set the JobId value as the JobIds parameter value. Specify the TargetPath parameter value. Provide the All parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Exporting Job Logs for Specific Period

|  |  |
| --- | --- |
| This example shows how to export logs for a job for a specific period. The cmdlet will export logs with the following settings:   * Logs will be exported for a job with the ID a19840ea-9cf5-413d-af29-57ecad85be9e.  * The export period of logs is set from 08/29/2025 10:00 AM to 11/15/2025 10:00 AM. * The cmdlet will export logs to the C:\Veeam\Office365\Logs folder.   |  | | --- | | Get-VBOJobSession  $datefrom = [datetime]"08/29/2025 10:00 AM"  $dateto = [datetime]"11/15/2025 10:00 AM"  Export-VBOJobLog -JobIds a19840ea-9cf5-413d-af29-57ecad85be9e -From $datefrom -To $dateto -TargetPath "C:\Veeam\Office365\Logs" |  Perform the following steps:   1. Run the [Get-VBOJobSession](get-vbojobsession.md) cmdlet. The cmdlet will return details of all Veeam Backup for Microsoft 365 jobs. Copy the JobId value from the cmdlet output. 2. Set the start date of the export period in the $datefrom variable and cast the date string to the datetime type. 3. Set the end date of the export period in the $dateto variable and cast the date string to the datetime type. 4. Run the Export-VBOJobLog cmdlet. Specify the following settings:  * Set the JobId value as the JobIds parameter value. * Set the $datefrom variable as the From parameter value. * Set the $dateto parameter as the To parameter value. * Specify the TargetPath parameter value. |

Related Commands

[Get-VBOJobSession](get-vbojobsession.md)


