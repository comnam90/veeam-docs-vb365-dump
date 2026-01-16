---
title: "get-vbodataretrievalobject"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbodataretrievalobject.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns objects whose backed-up data was retrieved from an object storage repository by retrieval job.

Syntax

|  |
| --- |
| Get-VBODataRetrievalObject -DataRetrieval <VBODataRetrieval> [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of objects whose backed-up data was retrieved from an object storage repository by the specified retrieval job.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| DataRetrieval | Specifies a retrieval job. The cmdlet will return objects whose backed-up data was retrieved by this retrieval job. | Accepts the VBODataRetrieval object.  To get this object, run the [Get-VBODataRetrieval](get-vbodataretrieval.md) cmdlet. | True | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Getting Retrieval Objects

This example shows how to get objects whose backed-up data was retrieved by the specified retrieval job.

|  |
| --- |
| $retrievaljob = Get-VBODataRetrieval -Id 3192dfc9-353f-468f-91b6-c66e5710c63f  Get-VBODataRetrievalObject -DataRetrieval $retrievaljob |

Perform the following steps:

1. Run the [Get-VBODataRetrieval](get-vbodataretrieval.md) cmdlet. Specify the Id parameter value. Save the result to the $retrievaljob variable.
2. Run the Get-VBODataRetrievalObject cmdlet with the $retrievaljob variable as the DataRetrieval parameter value.

Related Commands

[Get-VBODataRetrieval](get-vbodataretrieval.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
