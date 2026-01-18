---
title: "VBODataRetrieval"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbodataretrieval.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBODataRetrieval


Contains details about a data retrieval job.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Data retrieval job ID. |
| OrganizationId | GUID? | Microsoft organization ID. |
| OrganizationUniqueId | VBOOrganizationId | ID of the backed-up organization in the backup. |
| Name | String | Data retrieval job name. |
| Description | String | Data retrieval job description. |
| Repository | [VBORepository](vborepository.md) | Details about a backup repository. |
| PointInTime | DateTime | Point in time. |
| RetrievedRestorePoint | [VBORestorePoint](vborestorepoint.md) | Details about a restore point. |
| Type | VBODataRetrievalType | Data retrieval job type. Possible values:   * Exchange * OneDrive * SharePoint * Teams |
| ShowDeleted | Bool | If True, Veeam Backup for Microsoft 365 retrieves items that have been removed by user before the specified point in time. |
| ShowAllVersions | Bool | If True, Veeam Backup for Microsoft 365 retrieves all versions of items that have been modified by user before the specified point in time. |
| DataState | VBODataRetrievalDataState | Status of the backed-up data. Possible values:   * Retrieving * Retrieved * ChangingAvailabilityPeriod * Removing |
| LastStatus | VBODataRetrievalStatus | Data retrieval job status. Possible values:   * Stopped * Running * Succeeded * Failed * Warning * NotConfigured |
| StartTime | DateTime | Date and time when the data retrieval job was started. |
| ExpirationTime | DateTime? | Date and time when the retrieved data becomes unavailable. |
| EnableExpirationNotification | Bool | If True, Veeam Backup for Microsoft 365 notifies when the availability period is about to end. |
| ExpirationHoursThreshold | Int | Number of hours that should remain before the retrieved backed-up data expires to send a notification by email. |
| StorageType | VBODataRetrievalStorageType | Object storage type. Possible values:   * Azure * AmazonS3 |

Related Commands

* [Start-VBODataRetrieval](start-vbodataretrieval.md)
* [Get-VBODataRetrieval](get-vbodataretrieval.md)
* [Set-VBODataRetrieval](set-vbodataretrieval.md)
* [Get-VBODataRetrievalObject](get-vbodataretrievalobject.md)
* [Get-VBODataRetrievalSession](get-vbodataretrievalsession.md)


