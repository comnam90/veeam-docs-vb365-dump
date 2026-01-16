---
title: "get-vbouserprotectionreport"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbouserprotectionreport.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Generates reports on protected and unprotected user accounts of the Microsoft 365 and on-premises Microsoft organizations.

Syntax

|  |
| --- |
| Get-VBOUserProtectionReport [-Organization <VBOOrganization>] -Path <String> -Format <VBOReportFormat> [-Timezone <TimeZoneInfo>] [<CommonParameters>] |

Detailed Description

This cmdlet generates a report on user accounts of the Microsoft 365 and on-premises Microsoft organizations. This report contains statistical data on users considered protected, unprotected and unprotected with restore points.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will generate a report on user accounts of this organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | False | Named | False |
| Path | Specifies a path to the folder. The cmdlet will save a report to this folder. | String | True | Named | False |
| Format | Specifies in which format the cmdlet will save the report:   * PDF * CSV | VBOReportFormat | True | Named | False |
| Timezone | Specifies a timezone that you want to show in the report. The timezone is displayed at the bottom of the report page.  Note: If you do not provide this parameter, the cmdlet will generate a report in the UTC timezone. | Accepts the TimeZoneInfo object.  To get this object, run the [Get-TimeZone](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7.5) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Generating User Protection Report

|  |  |
| --- | --- |
| This example shows how to generate a report for users of the ABC Microsoft organization. The report is generated with the following settings:   * The cmdlet will save the report to the folder that is located at the following path: C:\tmp. * The cmdlet will generate the report in the CSV format. * The cmdlet will generate the report in the UTC timezone.   |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOUserProtectionReport -Path "C:\tmp" -Format CSV -Organization $org |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $org variable. 2. Run the Get-VBOUserProtectionReport cmdlet. Specify the following settings:  * Set the $org variable as the Organization parameter value. * Specify the Path parameter value. * Specify the Format parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Generating User Protection Report with Timezone

|  |  |
| --- | --- |
| This example shows how to generate a report for users of Microsoft organizations. The report is generated with the following settings:   * The cmdlet will save the report to the folder that is located at the following path: C:\share.  * The cmdlet will generate the report in the CSV format. * The cmdlet will generate the report in the specified timezone.   |  | | --- | | $timezone = Get-TimeZone  Get-VBOUserProtectionReport -Path "C:\share" -Format CSV -TimeZone $timezone |  Perform the following steps:   1. Run the [Get-TimeZone](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7.5) cmdlet. Save the result to the $timezone variable. 2. Run the Get-VBOUserProtectionReport cmdlet. Specify the following settings:  * Provide the Path parameter. * Provide the Format parameter. * Set the $timezone variable as the TimeZone parameter value. |

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-TimeZone](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7.5)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
