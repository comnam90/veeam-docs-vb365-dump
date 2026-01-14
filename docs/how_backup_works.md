---
title: "how_backup_works"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/how_backup_works.html"
last_updated: "8/15/2025"
product_version: "8.3.0.2201"
---


In this article

In Veeam Backup for Microsoft 365, data backup is conducted by a [backup proxy server](vbo_backup_proxy_servers.md) or a [backup proxy pool](vbo_proxy_pools.md) that logically groups several backup proxy servers. All necessary settings including restore points that Veeam Backup for Microsoft 365 collects from backup repositories, are saved to the Veeam Backup for Microsoft 365 configuration database created on a [PostgreSQL instance](architecture.md#postgresql).

If you save your backups locally in a JET-based backup repository, all data backup activities are performed by a particular backup proxy server. If you save your backups in an object storage repository — by a particular backup proxy server or a backup proxy pool. In case of using a backup proxy pool, the execution of backup operations is dynamically distributed among multiple backup proxy servers within the backup proxy pool.

In general, Veeam Backup for Microsoft 365 performs data backup in the following way:

1. The backup proxy server loads settings of a backup job from the Veeam Backup for Microsoft 365 configuration database, creates a job session and runs a backup job.
2. The backup proxy server connects to the Microsoft 365 organization using Microsoft Graph API and checks if the authentication is possible.

|  |
| --- |
| Note |
| To validate on-premises Microsoft organizations, Veeam Backup for Microsoft 365 uses PowerShell instead. |

1. The backup proxy server resolves objects added to the backup job and creates a list of objects to process.
2. The backup proxy server establishes a connection with a target backup repository and performs data transfer. During incremental job sessions, only those objects that have changed since the previous backup job session are processed, as long as no new objects are added to the backup job scope. If new objects that have not been backed up before are added to the backup job scope, the subsequent backup job session is considered a full run.

If data backup is performed to an object storage repository, the backup proxy server saves metadata of the backed-up objects to this object storage repository and updates the PersistentCache database. For more information about the PersistentCache database, see [Cache](understanding_cache.md).

1. The backup proxy server creates a restore point.

|  |
| --- |
| Note |
| Veeam Backup for Microsoft 365 provides a self-check mechanism that allows the product to validate if backed-up data appears in the object storage repository uncorrupted after compression and transfer. For more information, see [Data Validation](vbo_osr.md#datavalidation). |

Page updated 8/15/2025

Page content applies to build 8.3.0.2201
