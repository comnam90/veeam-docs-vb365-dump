---
title: "JET-based Backup Repositories and Object Storage Repositories"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/repositories.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# JET-based Backup Repositories and Object Storage Repositories


You can use the cmdlets from this section to perform the following operations with JET-based backup repositories and object storage repositories:

| Cmdlet | Operation |
| --- | --- |
| [Add-VBORepository](add-vborepository.md) | Adds a JET-based backup repository or an object storage repository to the Veeam Backup for Microsoft 365 infrastructure. |
| [Get-VBORepository](get-vborepository.md) | Returns backup repositories. |
| [Set-VBORepository](set-vborepository.md) | Modifies settings of a backup repository. |
| [Remove-VBORepository](remove-vborepository.md) | Removes backup repositories. |
| [Test-VBORepository](test-vborepository.md) | Verifies the integrity of backed-up Exchange, SharePoint and Teams data in backup repositories. |
| [Add-VBOAmazonS3CompatibleRepository](add-vboamazons3compatiblerepository.md) | Adds S3 Compatible object storage repository to the Veeam Backup for Microsoft 365 infrastructure. |
| [Set-VBOAmazonS3CompatibleRepository](set-vboamazons3compatiblerepository.md) | Modifies settings of S3 Compatible object storage repository. |
| [Add-VBOAmazonS3Repository](add-vboamazons3repository.md) | Adds Amazon S3 object storage repository (Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes) to the Veeam Backup for Microsoft 365 infrastructure. |
| [Set-VBOAmazonS3Repository](set-vboamazons3repository.md) | Modifies settings of Amazon S3 object storage repository (Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes). |
| [Add-VBOAmazonS3GlacierRepository](add-vboamazons3glacierrepository.md) | Adds Amazon S3 object storage repository (Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes) to the Veeam Backup for Microsoft 365 infrastructure. |
| [Set-VBOAmazonS3GlacierRepository](set-vboamazons3glacierrepository.md) | Modifies settings of Amazon S3 object storage repository (Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes). |
| [Add-VBOAzureBlobRepository](add-vboazureblobrepository.md) | Adds Azure Blob Storage to the Veeam Backup for Microsoft 365 infrastructure. |
| [Set-VBOAzureBlobRepository](set-vboazureblobrepository.md) | Modifies settings of Azure Blob Storage. |
| [Add-VBOAzureArchiveRepository](add-vboazurearchiverepository.md) | Adds Azure Blob Storage Archive to the Veeam Backup for Microsoft 365 infrastructure. |
| [Set-VBOAzureArchiveRepository](set-vboazurearchiverepository.md) | Modifies settings of Azure Blob Storage Archive. |
| [New-VBOAmazonS3CompatibleObjectStorageSettings](new-vboamazons3compatibleobjectstoragesettings.md) | Defines the S3 Compatible object storage repository settings. |
| [New-VBOAmazonS3ObjectStorageSettings](new-vboamazons3objectstoragesettings.md) | Defines the Amazon S3 object storage repository settings. |
| [New-VBOAzureBlobObjectStorageSettings](new-vboazureblobobjectstoragesettings.md) | Defines the Azure Blob Storage settings. |
| [Start-VBORepositorySynchronizeSession](start-vborepositorysynchronizesession.md) | Creates and starts a session to synchronize cache between object storage repositories and the PersistentCache database on the PostgreSQL instance. |
| [Get-VBORepositorySynchronizeSession](get-vborepositorysynchronizesession.md) | Returns sessions that are running to synchronize cache between object storage repositories and the PersistentCache database on the PostgreSQL instance. |
| [Stop-VBORepositorySynchronizeSession](stop-vborepositorysynchronizesession.md) | Stops sessions that are running to synchronize cache between object storage repositories and the PersistentCache database on the PostgreSQL instance. |
| [Start-VBORepositoryUpgradeSession](start-vborepositoryupgradesession.md) | Creates and starts a session to upgrade backup repositories. |
| [Get-VBORepositoryUpgradeSession](get-vborepositoryupgradesession.md) | Returns sessions started to upgrade backup repositories. |
| [Stop-VBORepositoryUpgradeSession](stop-vborepositoryupgradesession.md) | Stops sessions started to upgrade backup repositories. |
| [Start-VBORepositoryOwnerChangeSession](start-vborepositoryownerchangesession.md) | Creates and starts a change owner session to move a backup repository to another backup proxy server or backup proxy pool. |
| [Get-VBORepositoryOwnerChangeSession](get-vborepositoryownerchangesession.md) | Returns a change owner session started to move a backup repository to another backup proxy server or backup proxy pool. |
| [Stop-VBORepositoryOwnerChangeSession](stop-vborepositoryownerchangesession.md) | Stops change owner sessions. |
| [Start-VBORepositoryIndexingSession](start-vborepositoryindexingsession.md) | Creates and starts an indexing session when a backup proxy server collects and sends the restore points metadata of a backup repository associated with this backup proxy server to the Veeam Backup for Microsoft 365 controller. |

In This Section

[Object Storage Deprecated Cmdlets](object_storage_deprecated.md)


