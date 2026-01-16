---
title: "understanding_cache"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/understanding_cache.html"
last_updated: "8/29/2024"
product_version: "8.3.0.2201"
---


In this article

Cache helps you reduce costs incurred by your cloud storage provider when writing your data to the object storage repository or reading your data from the object storage repository.

For example, when you use Veeam Explorers to open backups located in the object storage repository, Veeam Backup for Microsoft 365 uses cache from which it retrieves the structure of the backed-up objects of your organizations. Such a structure is then loaded into the inventory pane of each of the Veeam Explorers so that you can navigate through it without actually downloading any data from the object storage repository.

Consider the following about cache:

* Cache is metadata that holds information about backed-up objects.
* Cache is created (or updated) during each backup session.
* Cache is saved to the PersistentCache database created by Veeam Backup for Microsoft 365 on the PostgreSQL instance. Metadata is saved separately for each object storage repository to the file located by default in the C:\Program Files\PostgreSQL\15\data folder on a machine with the PostgreSQL instance.

Veeam Backup for Microsoft 365 keeps cache synchronized between object storage repositories and the PersistentCache database.

Synchronization is required in the following cases:

* After you add a new object storage repository to the Veeam Backup for Microsoft 365 backup infrastructure, Veeam Backup for Microsoft 365 automatically creates the PersistentCache database for this object storage repository and saves cache.

* If the PersistentCache database not exist or has been accidentally removed or become damaged on the PostgreSQL instance, you can start the synchronization manually. For more information on how to synchronize cache, see [Synchronizing Cache](synch_repositories.md).

Page updated 8/29/2024

Page content applies to build 8.3.0.2201
