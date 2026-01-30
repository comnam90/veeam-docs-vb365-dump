---
title: "Get-VBOStorageConsumptionReport"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbostorageconsumptionreport.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---

# Get-VBOStorageConsumptionReport


Short Description

Generates reports on the Veeam Backup for Microsoft 365 storage consumption.

Syntax

|  |
| --- |
| Get-VBOStorageConsumptionReport -StartTime <DateTime> -EndTime <DateTime> -Path <String> -Format <VBOReportFormat> [-Timezone <TimeZoneInfo>] [<CommonParameters>] |

Detailed Description

This cmdlet generates reports on the Veeam Backup for Microsoft 365 storage consumption. This report contains details on used space in backup repositories.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| StartTime | Specifies the start date for the report period. The cmdlet will generate a report which contains information on the Veeam Backup for Microsoft 365 storage consumption for a period starting from the specified date. | DateTime | True | Named | False |
| EndTime | Specifies the end date for the report period. The cmdlet will generate a report which contains information on the Veeam Backup for Microsoft 365 storage consumption for a period ending on the specified date. | DateTime | True | Named | False |
| Path | Specifies a path to the folder. The cmdlet will save a report to this folder. | String | True | Named | False |
| Format | Specifies in which format the cmdlet will save the report:   * PDF * CSV | VBOReportFormat | True | Named | False |
| Timezone | Specifies a timezone that you want to show in the report. The timezone is displayed at the bottom of the report page.  Note: If you do not provide this parameter, the cmdlet will generate a report in the UTC timezone. | Accepts the TimeZoneInfo object.  To get this object, run the [Get-TimeZone](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7.5) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Generating Storage Consumption Report

|  |  |
| --- | --- |
| This command generates a report on the Veeam Backup for Microsoft 365 storage consumption with the following settings:   * The report period is set from 11/26/2023 to 11/26/2023. * The cmdlet will generate the report in the CSV format. * The cmdlet will generate the report in the UTC timezone.   |  | | --- | | Get-VBOStorageConsumptionReport -StartTime 01/01/2023 -EndTime 11/26/2023 -Path "C:\share" -Format CSV | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Generating Storage Consumption Report with Timezone

|  |  |
| --- | --- |
| This example shows how to generate a report on the Veeam Backup for Microsoft 365 storage consumption with the following settings:   * The report period is set from 01/01/2023 to 11/26/2023. * The cmdlet will generate the report in the CSV format. * The cmdlet will generate the report in the specified timezone.   |  | | --- | | $timezone = Get-TimeZone  Get-VBOStorageConsumptionReport -StartTime 01/01/2023 -EndTime 11/26/2023 -Path "C:\share" -Format CSV -TimeZone $timezone |  Perform the following steps:   1. Run the [Get-TimeZone](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7.5) cmdlet. Save the result to the $timezone variable.  1. Run the Get-VBOStorageConsumptionReport cmdlet. Specify the following settings:  * Provide the StartTime parameter. * Provide the EndTime parameter. * Provide the Path parameter. * Provide the Format parameter. * Set the $timezone variable as the TimeZone parameter value. |

Related Commands

[Get-TimeZone](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7.5)


