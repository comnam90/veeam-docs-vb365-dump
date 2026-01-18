---
title: "VBOUsageData"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbousagedata.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOUsageData


Contains details about the used space in a backup repository.

| Property | Type | Description |
| --- | --- | --- |
| RepositoryId | GUID | Backup repository ID. |
| Organization | VBOOrganizationData | ID of the backed-up organization in the backup. |
| UsedSpace | Ulong | Occupied space. |
| LocalCacheUsedSpace | Ulong | Space occupied by cache for object storage repository. |
| ObjectStorageUsedSpace | Ulong | Occupied space in object storage repository. |
| IsAvailable | Bool | If True, the backup repository is available for backup and restore. |
| Details | String | Details about the backup repository. |

Related Commands

[Get-VBOUsageData](get-vbousagedata.md)


