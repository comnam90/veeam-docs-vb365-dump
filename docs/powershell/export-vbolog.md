---
title: "export-vbolog"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/export-vbolog.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Exports the Veeam Backup for Microsoft 365 server log files.

Syntax

This cmdlet provides parameter sets that allow you to:

* Export all collected logs.

|  |
| --- |
| Export-VBOLog -ServerComponent <VBOServerComponent[]> [-All] -TargetPath <String> [<CommonParameters>] |

* Export logs for the specified time period.

|  |
| --- |
| Export-VBOLog -ServerComponent <VBOServerComponent[]> [-From <DateTime>] [-To <DateTime>] -TargetPath <String> [<CommonParameters>] |

* Export logs collected for the specified number of days.

|  |
| --- |
| Export-VBOLog -ServerComponent <VBOServerComponent[]> -DayPeriod <Int32> -TargetPath <String> [<CommonParameters>] |

Detailed Description

This cmdlet exports log files collected for the specified server components.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| ServerComponent | Specifies an array of the Veeam Backup for Microsoft 365 server components. The cmdlet will export logs of the specified server component. | Accepts the VBOServerComponent[] object.  To get this object, run the [Get-VBOServerComponents](get-vboservercomponents.md) cmdlet. | True | Named | False |
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

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Exporting All Logs Collected for Backup Proxy Server

|  |  |
| --- | --- |
| This example shows how to export all logs collected for a backup proxy server. The cmdlet will export logs with the following settings:   * Logs will be exported for a backup proxy server with the ID 06b7354e-518f-4a10-b4c1-98f49d743012.  * The cmdlet will export logs to the C:\Veeam\Office365\Logs folder.   |  | | --- | | $proxy = Get-VBOServerComponents -Name Proxy -Id 06b7354e-518f-4a10-b4c1-98f49d743012  Export-VBOLog -ServerComponent $proxy -TargetPath "C:\Veeam\Office365\Logs" -All |  Perform the following steps:   1. Run the [Get-VBOServerComponents](get-vboservercomponents.md) cmdlet. Specify the Name parameter value. Specify the Id parameter value. Save the result to the $proxy variable. 2. Run the Export-VBOLog cmdlet. Set the $proxy variable as the ServerComponent parameter value. Specify the TargetPath parameter value. Provide the All parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Exporting Logs for Backup Proxy Server for Specific Period

|  |  |
| --- | --- |
| This example shows how to export logs for a backup proxy server for a specific period. The cmdlet will export logs with the following settings:   * Logs will be exported for a backup proxy server with the ID 06b7354e-518f-4a10-b4c1-98f49d743012. * The export period of logs is set from 08/29/2023 10:00 AM to 11/15/2023 10:00 AM. * The cmdlet will export logs to the C:\Veeam\Office365\Logs folder.   |  | | --- | | $proxy = Get-VBOServerComponents -Name Proxy -Id 06b7354e-518f-4a10-b4c1-98f49d743012  $datefrom = [datetime]"08/29/2023 10:00 AM"  $dateto = [datetime]"11/15/2023 10:00 AM"  Export-VBOLog -ServerComponent $proxy -From $datefrom -To $dateto -TargetPath "C:\Veeam\Office365\Logs" |  Perform the following steps:   1. Run the [Get-VBOServerComponents](get-vboservercomponents.md) cmdlet. Specify the Name parameter value. Specify the Id parameter value. Save the result to the $proxy variable. 2. Set the start date of the export period in the $datefrom variable and cast the date string to the datetime type. 3. Set the end date of the export period in the $dateto variable and cast the date string to the datetime type. 4. Run the Export-VBOLog cmdlet. Specify the following settings:  * Set the $proxy variable as the ServerComponent parameter value. * Set the $datefrom variable as the From parameter value. * Set the $dateto parameter as the To parameter value. * Specify the TargetPath parameter value. |

Related Commands

[Get-VBOServerComponents](get-vboservercomponents.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
