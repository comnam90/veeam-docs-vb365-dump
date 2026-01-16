---
title: "get-vbodataretrieval"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbodataretrieval.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns retrieval jobs.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get a retrieval job by the retrieval job ID.

|  |
| --- |
| Get-VBODataRetrieval -Id <Guid> [<CommonParameters>] |

* Get retrieval jobs by the associated backup repository or Microsoft organization or status of the backed-up data.

|  |
| --- |
| Get-VBODataRetrieval [-Repository <VBORepository>] [-Organization <VBOOrganization>] [-DataState <VBODataRetrievalDataState>] [<CommonParameters>] |

Detailed Description

This cmdlet returns retrieval jobs configured in Veeam Backup for Microsoft 365.

Run the [Get-VBODataRetrievalSession](get-vbodataretrievalsession.md) cmdlet to get retrieval job IDs.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Id | Specifies an ID of the retrieval job. The cmdlet will return the retrieval job with this ID. | Guid | True | Named | False |
| Repository | Specifies the object storage repository that was specified as a target for backup copy jobs. The cmdlet will return retrieval jobs for backed-up data stored in this object storage repository. | Accepts the VBORepository object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | False | Named | True (ByValue) |
| Organization | Specifies a Microsoft organization. The cmdlet will return retrieval jobs for backed-up data of objects from this organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | False | Named | False |
| DataState | Specifies a status of the backed-up data. The cmdlet will return retrieval jobs in which data has the specified status. You can select the following statuses:   * Retrieving * Retrieved * ChangingAvailabilityPeriod * Removing | VBODataRetrievalDataState | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBODataRetrieval object that contains settings for a retrieval job.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Retrieval Job by ID

|  |  |
| --- | --- |
| This command returns a retrieval job by ID.  |  | | --- | | Get-VBODataRetrieval -Id f5fda89f-40a2-4d1c-8e05-f6bba94b6c50 | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Retrieval Job by Backup Repository and Data Status

|  |  |
| --- | --- |
| This example shows how to get a list of retrieval jobs in which backed-up data is stored in the Azure Archive Storage object storage repository and has the Retrieved status.  |  | | --- | | $repository = Get-VBORepository -Name "Azure Archive Storage"  Get-VBODataRetrieval -Repository $repository -DataState Retrieved |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable. 2. Run the Get-VBODataRetrieval cmdlet. Set the $repository variable as the Repository parameter value. Specify the DataState parameter value. |

Related Commands

* [Get-VBODataRetrievalSession](get-vbodataretrievalsession.md)
* [Get-VBORepository](get-vborepository.md)
* [Get-VBOOrganization](get-vboorganization.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
