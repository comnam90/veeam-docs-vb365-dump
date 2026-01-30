---
title: "Storage for Backup Copies"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/osr_archive_structure.html"
last_updated: "8/30/2024"
product_version: "8.3.0.2201"
---

# Storage for Backup Copies


The following table lists the structure that is created and maintained by Veeam Backup for Microsoft 365 in object storage repositories where you transfer your backed-up data using backup copy. You can use any supported object storage for this purpose. For more information, see [Object Storage Repositories](vbo_osr.md).

| Directory | Description |
| --- | --- |
| <bucket\_name/container\_name> | A bucket or container name.  Buckets and containers must be created in advance using the cloud provider tools. Veeam Backup for Microsoft 365 does not support creating new buckets or containers. |
| <bucket\_name/container\_name>/Veeam/Backup365/ | A set of mandatory folders created by Veeam Backup for Microsoft 365. |
| <repository\_folder\_name> | A repository folder that you create when adding a new object storage repository.  For more information on how to add a new object storage repository, see [Adding Object Storage Repositories](adding_object_storage.md). |
| <repository\_folder\_name>/CommonInfo | Contains the following blob files:   * [Blob file] StorageStatistics. Contains information on used space in the object storage repository per organization. * [Blob file] RepositoryConfig. Contains the object storage repository configuration such as the retention type, the data immutability settings and other auxiliary information, as well as version of the blob file. |
| <repository\_folder\_name>/CriticalDataBackup | Contains identical copies of the following blob files:   * [Blob file] RepositoryConfig. Contains the object storage repository configuration such as the retention type, the data immutability settings and other auxiliary information, as well as version of the blob file. * [Blob file] BackupKeys. Contains information about the encryption keys that you set to encrypt data in object storage, as well as version of the blob file. |
| <repository\_folder\_name>/DataRetrievalsMetadata | Contains information about backed-up data retrievals. |
| <repository\_folder\_name>/Encryption | Contains the BackupKeys blob file that holds information about the encryption keys that you set to encrypt data in object storage, as well as version of the blob file. |
| <repository\_folder\_name>/OrganizationInfos | Contains blob files with the information about archived Microsoft organizations. |
| <repository\_folder\_name>/Organizations | The root folder that contains archived Microsoft organizations. Each organization is kept in its own folder with a unique identification number. |
| <organization\_Id>/AccountMailboxes | Contains blob files with the information about account mailboxes. |
| <organization\_Id>/CopyObjects | Contains dates of the latest attempt of saving backed-up data of objects per object. |
| <organization\_Id>/Mailboxes/<mailbox\_Id> | The Mailboxes directory contains archived Exchange mailboxes. Each mailbox is saved under a unique identification number to the <mailbox\_Id> directory.  The <mailbox\_Id> directory contains the following directories:   * Messages. Contains archived Exchange data. * Folders. Contains a snapshot of Exchange folders at the specified point in time. |
| <organization\_Id>/MailboxInfos | Contains blob files with the information about archived Exchange mailboxes. |
| <organization\_Id>/RestorePoints | Contains blob files with the information about restore points created by Veeam Backup for Microsoft 365 and a list of restore point objects per restore point. |
| <organization\_Id>/Retrievals | Contains blob files with the information about backed-up data that was retrieved. |
| <organization\_Id>/SiteInfo | Contains blob files with the information about archived SharePoint sites. |
| <organization\_Id>/Sites | Contains a blob file with a list of archived SharePoint sites. |
| <organization\_Id>/TeamInfos | Contains blob files with the unchanged information about teams. |
| <organization\_Id>/Teams | Contains the following directories:   * Accounts. Contains names and descriptions of all users included in all teams. * <team\_Id>. Contains archived Microsoft Teams data such as Channels, Tabs, Applications and UsersMembership. |
| <organization\_Id>/WebRestorePoints | Contains information on how web objects were backed up per restore point. |
| <organization\_Id>/Webs/<web\_Id> | A set of folders that contain archived SharePoint sites and OneDrive Items.  The <web\_Id> directory contains the following directories:   * Files. Contains archived files of the SharePoint site. * WebParts. Contains Web Parts of SharePoint sites. * Items. Contains archived items such as those located under the Subsites and Content folders for SharePoint, and users folders for OneDrive. * Lists. Contains archived SharePoint lists. * ListViews. Contains archived SharePoint list views. |
| <repository\_folder\_name>/RepositoryLock | Contains a lock file denoting that the object storage repository is in use by a backup proxy server or a backup proxy pool. Access to the object storage repository metadata is limited. |


