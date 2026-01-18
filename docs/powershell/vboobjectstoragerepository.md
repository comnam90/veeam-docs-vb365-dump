---
title: "VBOObjectStorageRepository"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboobjectstoragerepository.html"
last_updated: "12/18/2025"
product_version: "8.3.0.2201"
---

# VBOObjectStorageRepository


Contains details about an object storage repository.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Object storage repository ID. |
| Name | String | Object storage repository name. |
| Description | String | Object storage repository description. |
| Type | VBOObjectStorageRepositoryType | Object storage repository type. Possible values:   * LocalObjectStorage * AzureBlob * AmazonS3 * AmazonS3Compatible * IBMCloud * WasabiCloud |
| EnableSizeLimit | Bool | If True, a soft limit in GB for the object storage repository consumption is enabled. |
| SizeLimit | Ulong | Soft limit in GB for the object storage repository consumption. |
| UsedSpace | Ulong | Used space in Bytes. |
| FreeSpace | Ulong? | Free space in Bytes. |
| IsLongTerm | Bool | If True, the object storage repository belongs to Azure Blob Storage Archive access tier or any of the Amazon S3 Glacier storage classes. |
| EnableImmutability | Bool | If True, the immutability feature is enabled. |
| EnableImmutabilityGovernanceMode | Bool | If True, a storage administrator with specific permissions is allowed to override the lock settings and to delete the protected backups in the object storage repository. |
| ImmutabilityPeriod | Int | Number of days when your data are blocked for deletion or modification. |
| EnableDefragmentation | Bool | If True, defragmentation is enabled for the object storage repository. |

Related Commands

* [Add-VBORepository](add-vborepository.md)
* [Get-VBOObjectStorageRepository](get-vboobjectstoragerepository.md)
* [Set-VBOObjectStorageRepository](set-vboobjectstoragerepository.md)
* [Remove-VBOObjectStorageRepository](remove-vboobjectstoragerepository.md)


