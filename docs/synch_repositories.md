---
title: "synch_repositories"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/synch_repositories.html"
last_updated: "8/30/2024"
product_version: "8.3.0.2201"
---


In this article

You can manually synchronize cache between object storage repositories and the PersistentCache database on the PostgreSQL instance.

Such synchronization is required when an object storage repository has the Out of Sync state. This state is assigned if the PersistentCache database in which Veeam Backup for Microsoft 365 saves [cache](understanding_cache.md) for this object storage repository not exist or has been removed or become damaged.

Once cache is synchronized, you can do the following:

* Open and restore data from backups located in the object storage repository.

Backups located in the object storage repository become available for browsing and restore. For more information, see [Exploring Single Organization](vbo_exploring_single_organization.md) and [Exploring All Organizations](vbo_exploring_all_organizations.md).

* Back up data to the object storage repository. For more information, see [Data Backup](vbo_data_backup.md).

To synchronize cache between an object storage repository and the PersistentCache database, do the following:

1. Open the Backup Infrastructure view.
2. In the inventory pane, select the Backup Repositories > Out of Sync node.
3. In the preview pane, do one of the following:

* Select an object storage repository and click Synchronize Repository on the ribbon.

* Right-click an object storage repository and select Synchronize.

During synchronization, Veeam Backup for Microsoft 365 downloads metadata (cache) from the object storage repository to the PersistentCache database created for this object storage repository on the PostgreSQL instance. For more information about cache, see [Cache](understanding_cache.md).

If you want to stop synchronization, click Stop Sync on the ribbon.

[![Synchronizing Backup Repositories](images/synchronizing_tiers.webp)](images/synchronizing_tiers.webp "Synchronizing Backup Repositories")

Related Topics

[Object Storage Repositories](vbo_osr.md)

Page updated 8/30/2024

Page content applies to build 8.3.0.2201
