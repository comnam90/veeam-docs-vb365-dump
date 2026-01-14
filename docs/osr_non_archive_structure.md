---
title: "osr_non_archive_structure"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/osr_non_archive_structure.html"
last_updated: "8/29/2024"
product_version: "8.3.0.2201"
---


In this article

The following table lists the structure that is created and maintained by Veeam Backup for Microsoft 365 in object storage repositories where you store your backups.

You can use S3 Compatible object storage repository, Azure Blob Storage Hot/Cool access tiers, Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes for this purpose.

Keep in mind that Veeam Backup for Microsoft 365 does not support this structure for Azure Blob Storage Archive access tier and all Amazon S3 Glacier storage classes, and you cannot target a backup job to them.

|  |
| --- |
| Note |
| In versions 8 and 7, Veeam Backup for Microsoft 365 creates the storage structure for backups in different formats. Veeam Backup for Microsoft 365 version 8 supports both formats: you can continue to use object storage created by version 7 to back up, restore and explore data. For more information about the object storage structure created for backup storage by Veeam Backup for Microsoft 365 version 7, see [Storage for Backups](https://helpcenter.veeam.com/archive/vbo365/70/guide/osr_non_archive_structure.html?ver=80). |

dd

| Directory | Description |
| --- | --- |
| <bucket\_name/container\_name> | A bucket or container name.  Buckets and containers must be created in advance using the cloud provider tools. Veeam Backup for Microsoft 365 does not support creating new buckets or containers. |
| <bucket\_name/container\_name>/Veeam/Backup365/ | A set of mandatory folders created by Veeam Backup for Microsoft 365. |
| <repository\_folder\_name> | A repository folder that you create when adding a new object storage repository.  For more information on how to add a new object storage repository, see [Adding Object Storage Repositories](adding_object_storage.md). |
| <repository\_folder\_name>/CommonInfo | Contains the following directories and blob files:   * [Directory] RestorePoints. Contains information about available restore points for Microsoft Exchange. * [Directory] WebRestorePoints. Contains information about available restore points for Microsoft SharePoint and OneDrive for Business.   Both directories keep a blob file that contains a list of available restore points. If the size of a blob file is greater 4 MB, another blob file is created.   * [Blob file] Organizations. Contains a list of backed-up organizations. * [Blob file] RepositoryConfig. Contains the object storage repository configuration such as the retention type, the data immutability settings and other auxiliary information. |
| <repository\_folder\_name>/CriticalDataBackup | Contains identical copies of the following blob files:   * [Blob file] Organizations. Contains a list of backed-up organizations. * [Blob file] RepositoryConfig. Contains the object storage repository configuration such as the retention type, the data immutability settings and other auxiliary information. * [Blob file] BackupKeys. Contains information about the encryption keys that you set to encrypt data in object storage. |
| <repository\_folder\_name>/Encryption | Contains the BackupKeys blob file that holds information about the encryption keys that you set to encrypt data in object storage. |
| <repository\_folder\_name>/Organizations | The root folder that contains backed-up Microsoft organizations. Each organization is kept in its own folder with a unique identification number. |
| Organizations/<organization\_Id> | The <organization\_Id> directory contains backed-up data of a particular Microsoft organization. |
| <organization\_Id>/Mailboxes/<mailbox\_Id> | The Mailboxes directory contains backed-up Exchange mailboxes and a blob file that holds information about all backed-up mailboxes. Each mailbox is saved under a unique identification number to the <mailbox\_Id> directory.  The <mailbox\_Id> directory contains the following directories:   * Folders. Contains backed-up Exchange folders, information about folder changes and information required to load the backup contents into the Veeam Explorer for Microsoft Exchange scope. * ItemsChanges. Contains indexes of backed-up Exchange items. This information is used to search for items in the object storage repository. * ItemsData. Contains blob data of backed-up Exchange items. For example, attachments are saved to this folder. * ItemsPreview. Contains metadata and properties of backed-up Exchange items. |
| <organization\_Id>/RestorePointObjects | Contains blob files with a list of objects (mailboxes, sites, and teams) that were backed up by Veeam Backup for Microsoft 365 per a particular restore point at the specified point in time. |
| <organization\_Id>/Sites | Contains a blob file with a list of backed-up SharePoint sites, a list of backed-up SharePoint site collections, information about user accounts which personal sites (SharePoint and OneDrive) was backed up, and information required to load the backup contents into the Veeam Explorer for Microsoft SharePoint scope. |
| <organization\_Id>/Teams | The Teams directory contains the following directories with information about backed-up Microsoft Teams data:   * <team\_Id>. Contains backed-up Microsoft Teams data of a particular team. * Accounts. Contains a blob file with names and descriptions of all users included in all teams at the moment of the latest backup. * TeamInfos. Contains unchanged information about teams, as well as team changes and information about team Applications at the specified point in time. |
| <organization\_Id>/Teams/<team\_Id> | The <team\_Id> directory contains backed-up Microsoft Teams data of a particular team.  The <team\_Id> directory contains the following directories:   * Channels. Contains a blob file with information about backed-up team channels. * Posts. Contains backed-up team posts including the Parents directory with information about parent posts and the Replies directory with information about replies. Also, contains required data to load the backup contents into the Veeam Explorer for Microsoft Teams scope. * Tabs. Contains a blob file with information about backed-up tabs. * Users. Contains a blob file with information about backed-up users. |
| <organization\_Id>/WebBackups | Contains a list of SharePoint sites to be loaded into the Veeam Explorer for Microsoft SharePoint scope. |
| <organization\_Id>/WebData | Contains data that is required to restore SharePoint sites. |
| <organization\_Id>/WebPreview | Contains data that is required to display SharePoint sites when exploring backups with Veeam Explorer for Microsoft SharePoint. Required for a snapshot-based retention policy. |
| <organization\_Id>/Webs/<web\_Id> | A set of folders that contain backed-up SharePoint sites.  The <web\_Id> directory contains the following directories:   * Files. Contains files of the SharePoint site. * Items. Contains SharePoint list items. * Lists. Contains SharePoint lists. * ListsData. Contains properties of SharePoint lists. * ListViews. Contains SharePoint list views. |
| <repository\_folder\_name>/RepositoryLock | Contains a lock file denoting that the object storage repository is in use by a backup proxy server or a backup proxy pool. Access to the object storage repository metadata is limited. |

Page updated 8/29/2024

Page content applies to build 8.3.0.2201
