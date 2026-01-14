---
title: "vbo_removing_repository"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_removing_repository.html"
last_updated: "8/29/2024"
product_version: "8.3.0.2201"
---


In this article

Veeam Backup for Microsoft 365 allows you to remove backup repositories from the Veeam Backup for Microsoft 365 backup infrastructure if you no longer need them.

Consider the following:

* When removing a backup repository, backup files that reside in such a repository will not be removed.

* The last remaining backup repository cannot be removed.

* You cannot remove a backup repository that is in use by backup jobs.

To remove such a repository, remove (or re-map) all backup jobs that are mapped to this repository and then remove a repository. For more information on how to remove a backup job, see [Removing Backup Job](removing_backup_job.md).

* You cannot remove an object storage repository that is in use by backup copy jobs or retrieval jobs.

To remove a backup repository, do the following:

1. Open the Backup Infrastructure view.
2. In the inventory pane, select one of the following nodes:

* Backup Repositories. Contains all backup repositories added to the Veeam Backup for Microsoft 365 backup infrastructure.
* Object storage. Contains S3 Compatible object storage repositories, Azure Blob Storage Hot/Cool access tiers, Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes.
* Local disk. Contains Default Backup Repository and other JET-based backup repositories.
* Archive. Contains Azure Blob Storage Archive access tier and all Amazon S3 Glacier storage classes.

1. In the preview pane, do one of the following:

* Select a backup repository and click Remove Repository on the ribbon.

* Right-click a backup repository and select Remove.

[![Removing Backup Repository](images/removing_repo.webp)](images/removing_repo.webp "Removing Backup Repository")

Page updated 8/29/2024

Page content applies to build 8.3.0.2201
