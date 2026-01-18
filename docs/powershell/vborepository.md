---
title: "VBORepository"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vborepository.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBORepository


Contains details about a Veeam Backup for Microsoft 365 backup repository.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Backup repository ID. |
| Proxy | [VBOProxy](vboproxy.md) | Details about a backup proxy server associated with the backup repository. |
| ProxyPool | [VBOProxyPool](vboproxypool.md) | Details about a backup proxy pool associated with the backup repository. |
| Name | String | Backup repository name. |
| Description | String | Backup repository description. |
| Path | String | Path to the directory where backups are stored. |
| Capacity | Ulong | Size of the JET-based backup repository in Bytes. |
| FreeSpace | Ulong | Available space on the JET-based backup repository in Bytes. |
| RetentionPeriod | VBORetentionPeriod | Retention period in years. Possible values:   * Year1 * Years2 * Years3 * Years5 * Years7 * Years10 * Years25 * KeepForever |
| RetentionType | VBORetentionType | Retention policy type. Possible values:   * ItemLevel * SnapshotBased |
| CustomRetentionPeriodType | VBORetentionPeriodType | Custom retention period. Possible values:   * Months * Days |
| RetentionFrequencyType | VBORetentionFrequencyType | Retention policy schedule. Possible values:   * Monthly * Daily |
| DailyTime | TimeSpan | For daily retention policy schedule.  Time of the day when the retention policy must be applied. |
| DailyType | VBODailyType | For daily retention policy schedule.  Days when the retention policy must be applied. Possible values:   * Everyday * Workdays * Weekends * Monday * Tuesday * Wednesday * Thursday * Friday * Saturday * Sunday |
| MonthlyTime | TimeSpan | For monthly retention policy schedule.  Time of the day when the retention policy must be applied. |
| MonthlyDayNumber | VBOMonthlyDayNumber | For monthly retention policy schedule.  Order number for the day of the week when the retention policy must be applied. Possible values:   * First * Second * Third * Fourth * Last |
| MonthlyDayOfWeek | DayOfWeek | For monthly retention policy schedule.  Day of the week when the retention policy must be applied. Possible values:   * Sunday * Monday * Tuesday * Wednesday * Thursday * Friday * Saturday |
| ObjectStorageRepository | [VBOObjectStorageRepository](vboobjectstoragerepository.md) | Details about the object storage repository. |
| EnableObjectStorageEncryption | Bool | If True, encryption of data stored in the object storage repository is enabled. |
| ObjectStorageEncryptionKey | [VBOEncryptionKey](vboencryptionkey.md) | Details about the object storage encryption key. |
| IsOutdated | Bool | If True, the backup repository has the Out of Date state and must be upgraded. |
| IsOutOfSync | Bool | If True, the object storage repository has the Out of Sync state. |
| IsOutOfOrder | Bool | If True, the backup repository has the Invalid state. |
| IsIndexed | Bool | If True, the backup repository was indexed. |
| OutOfOrderReason | String | Reason why the backup repository has the Invalid state. |
| IsLongTerm | Bool | If True, the backup repository is an object storage repository and belongs to Azure Blob Storage Archive access tier or any of the Amazon S3 Glacier storage classes. |
| IsObjectStorage | Bool | If True, backup repository is the object storage repository. |

Related Commands

* [Add-VBORepository](add-vborepository.md)
* [Get-VBORepository](get-vborepository.md)
* [Set-VBORepository](set-vborepository.md)
* [Remove-VBORepository](remove-vborepository.md)
* [Test-VBORepository](test-vborepository.md)
* [Set-VBOAmazonS3CompatibleRepository](set-vboamazons3compatiblerepository.md)
* [Set-VBOAmazonS3Repository](set-vboamazons3repository.md)
* [Set-VBOAmazonS3GlacierRepository](set-vboamazons3glacierrepository.md)
* [Set-VBOAzureBlobRepository](set-vboazureblobrepository.md)
* [Set-VBOAzureArchiveRepository](set-vboazurearchiverepository.md)
* [Start-VBORepositorySynchronizeSession](start-vborepositorysynchronizesession.md)
* [Get-VBORepositorySynchronizeSession](get-vborepositorysynchronizesession.md)
* [Start-VBORepositoryUpgradeSession](start-vborepositoryupgradesession.md)
* [Get-VBORepositoryUpgradeSession](get-vborepositoryupgradesession.md)
* [Start-VBORepositoryOwnerChangeSession](start-vborepositoryownerchangesession.md)
* [Start-VBORepositoryIndexingSession](start-vborepositoryindexingsession.md)
* [Add-VBOJob](add-vbojob.md)
* [Set-VBOJob](set-vbojob.md)
* [Add-VBOCopyJob](add-vbocopyjob.md)
* [Get-VBOCopyJob](get-vbocopyjob.md)
* [Set-VBOCopyJob](set-vbocopyjob.md)
* [Get-VBORestorePoint](get-vborestorepoint.md)
* [Get-VBOEntityData](get-vboentitydata.md)
* [Move-VBOEntityData](move-vboentitydata.md)
* [Remove-VBOEntityData](remove-vboentitydata.md)
* [Get-VBOUsageData](get-vbousagedata.md)
* [Get-VBODataRetrieval](get-vbodataretrieval.md)


