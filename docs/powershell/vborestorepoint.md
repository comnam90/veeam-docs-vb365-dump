---
title: "VBORestorePoint"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vborestorepoint.html"
last_updated: "1/9/2026"
product_version: "8.3.0.2201"
---

# VBORestorePoint


Contains details about a restore point.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Restore point ID. |
| RepositoryId | GUID | Backup repository ID. |
| BackupTime | DateTime | Date and time when the restore point was created. |
| JobId | GUID | Job ID. |
| RetrievalId | GUID | Data retrieval job ID. |
| OrganizationId | GUID | Microsoft organization ID. |
| IsExchange | Bool | If True, the restore point contains Microsoft Exchange data. |
| IsSharePoint | Bool | If True, the restore point contains Microsoft SharePoint data. |
| IsOneDrive | Bool | If True, the restore point contains Microsoft OneDrive data. |
| IsTeams | Bool | If True, the restore point contains Microsoft Teams data. |
| IsLongTermCopy | Bool | If True, the restore point was created by a backup copy job in one of the following object storage repositories: Azure Blob Storage Archive access tier, Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval or Amazon S3 Glacier Deep Archive storage classes. |
| IsRetrieved | Bool | If True, the restore point was retrieved from object storage repositories by a data retrieval job. |
| IsRetrievable | Bool | If True, the restore point can be retrieved. |
| IsCopy | Bool | If True, the restore point was created by a backup copy job in any object storage repository. |
| ImmutabilityExpiresOn | DateTime? | Date and time until which the backed-up data in the restore point are blocked for deletion or modification. |

Related Commands

* [Get-VBOEntityData](get-vboentitydata.md)
* [Start-VBODataRetrieval](start-vbodataretrieval.md)


