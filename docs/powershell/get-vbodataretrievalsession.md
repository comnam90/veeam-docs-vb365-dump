---
title: "get-vbodataretrievalsession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbodataretrievalsession.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns data retrieval sessions.

Syntax

|  |
| --- |
| Get-VBODataRetrievalSession [-Retrieval <VBODataRetrieval>] [-Status <VBOJobStatus>] [-Last] [<CommonParameters>] |

Detailed Description

This cmdlet returns data retrieval sessions.

Data retrieval session record contains the following information:

* Id — specifies the system ID of the data retrieval session.
* RetrievalId — specifies the system ID of the retrieval job.
* Name — specifies the retrieval job name.
* CreationTime — specifies date and time when the data retrieval session was created.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Retrieval | Specifies a retrieval job. The cmdlet will return the data retrieval session that includes this retrieval job. | Accepts the VBODataRetrieval object.  To get this object, run the [Get-VBODataRetrieval](get-vbodataretrieval.md) cmdlet. | False | Named | True (ByValue) |
| Status | Specifies the retrieval job status. The cmdlet will return data retrieval sessions for the retrieval jobs with the specified status:   * Stopped * Running * Success * Failed * Warning * NotConfigured * Disconnected * Queued | VBOJobStatus | False | Named | False |
| Last | Defines that the cmdlet will return the latest data retrieval session.  If the Retrieval parameter is used, the cmdlet will return the latest data retrieval session for the specified retrieval job.  If the Status parameter is used, the cmdlet will return the latest data retrieval session for the retrieval jobs with the specified status.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Data Retrieval Sessions

|  |  |
| --- | --- |
| This command returns a list of all data retrieval sessions.  |  | | --- | | Get-VBODataRetrievalSession | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Data Retrieval Sessions by Backup Repository and Data Status

|  |  |
| --- | --- |
| This example shows how to get all data retrieval sessions for retrieval jobs in which backed-up data is stored in the Azure Archive Storage object storage repository and has the Retrieved status.  |  | | --- | | $repository = Get-VBORepository -Name "Azure Archive Storage"  $retrievaljob = Get-VBODataRetrieval -Repository $repository -DataState Retrieved  Get-VBODataRetrievalSession -Retrieval $retrievaljob |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable. 2. Run the [Get-VBODataRetrieval](get-vbodataretrieval.md) cmdlet. Set the $repository variable as the Repository parameter value. Specify the DataState parameter value. Save the result to the $retrievaljob variable. 3. Run the Get-VBODataRetrievalSession cmdlet with the $retrievaljob variable. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Latest Data Retrieval Session

|  |  |
| --- | --- |
| This command returns the latest data retrieval session stored in Veeam Backup for Microsoft 365.  |  | | --- | | Get-VBODataRetrievalSession -Last | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Getting Latest Data Retrieval Session by Retrieval Job Status

|  |  |
| --- | --- |
| This command returns the latest data retrieval session for the retrieval jobs with the Failed status.  |  | | --- | | Get-VBODataRetrievalSession -Status Failed -Last | |

Related Commands

* [Get-VBODataRetrieval](get-vbodataretrieval.md)
* [Get-VBORepository](get-vborepository.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
