---
title: "VBODataRetrievalSession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbodataretrievalsession.html"
last_updated: "1/9/2026"
product_version: "8.3.0.2201"
---

# VBODataRetrievalSession


Contains details about a data retrieval session.

| Property | Type | Description |
| --- | --- | --- |
| RetrievalId | GUID | Data retrieval job ID. |
| RepositoryId | GUID | Backup repository ID. |
| Name | String | Data retrieval job name. |
| Type | VBODataRetrievalSessionType | Type of the data retrieval session. Possible values:   * Retrieve * RetrievalChangeAvailabilityPeriodDays * RetrievalRemoving |
| Status | VBODataRetrievalStatus | Data retrieval job status. Possible values:   * Stopped * Running * Succeeded * Failed * Warning * NotConfigured |
| ProcessedObjects | Long | Number of objects processed by the data retrieval session. |
| ProxyId | GUID? | Backup proxy server ID. |
| ProxyPoolId | GUID? | Backup proxy pool ID. |

Related Commands

[Get-VBODataRetrievalSession](get-vbodataretrievalsession.md)


