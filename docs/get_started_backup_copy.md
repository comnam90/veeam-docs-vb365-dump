---
title: "get_started_backup_copy"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/get_started_backup_copy.html"
last_updated: "9/2/2024"
product_version: "8.3.0.2201"
---


In this article

In general, the process of creating backup copies in Veeam Backup for Microsoft 365 involves the following steps:

1. [Planning and preparation](#prepare).

You can skip this step in whole or in part if necessary backup infrastructure components are already added to Veeam Backup for Microsoft 365.

1. [Create a backup job](#backup).
2. [Create a backup copy job](#backup_copy).

After Veeam Backup for Microsoft 365 created backup copies, you can explore and restore, or retrieve backup copies. For more information, see [What You Do with Backup Copies](#what_next).

Planning and Preparation

Before you start creating a backup copy job to protect your backups, add the following object storage repositories in the Veeam Backup for Microsoft 365 backup infrastructure:

* Object storage repository where you want to store your backups.

* Object storage repository that you want to use as a target for backup copy jobs.

For more information, see [Object Storage Usage Scenarios](vbo_osr.md#usage_scenarios) and [Adding Object Storage Repositories](adding_object_storage.md).

Consider the following:

* Azure Blob Storage Archive access tier, Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes are supported only to store backup copies. For more information, see [Adding Amazon S3 Object Storage Repositories](adding_amazon_s3_storage.md) and [Adding Microsoft Azure Blob Storage](adding_azure_storage.md).
* The object storage repository where you store your backups and the object storage repository where you store backup copies must be associated with the same backup proxy server or backup proxy pool and have the same retention type.

Creating Backup Job

Create a backup job. In the backup job settings, specify an object storage repository where you want to store your backups. For more information, see [Specify Backup Repository](specify_backup_proxy_server.md).

Creating Backup Copy Job

Create a backup copy job for the backup job created at the [Creating Backup Job](#backup) step. In the backup copy job settings, specify an object storage repository where Veeam Backup for Microsoft 365 will copy your backed-up data. For more information, see [Select Target Backup Repository](target_backup_copy_repo.md).

What You Do with Backup Copies

After Veeam Backup for Microsoft 365 created backup copies, you can do the following:

* Retrieve your backup copies.

Retrieving backed-up data from backup copies is required before data explore and restore if Veeam Backup for Microsoft 365 stores this data in Azure Blob Storage Archive access tier, Amazon S3 Glacier Flexible Retrieval, or Amazon S3 Glacier Deep Archive storage classes. For more information, see [Retrieving Backed-Up Data](retrieving_backed_up_files.md), [Exploring Retrieved Data](vbo_exploring_retrieved.md) and [Data Restore](vbo_data_restore.md).

|  |
| --- |
| Note |
| If you store backup copies in the object storage repository of Amazon S3 Glacier Instant Retrieval storage class, you can explore and restore your backed-up data directly from this object storage repository. You do not need to retrieve backed-up data from Amazon S3 Glacier Instant Retrieval storage class. |

* Explore and restore backup copies.

You can start exploring and restoring data at any time you want if you have copied your backed-up data to the following object storage repositories:

* Azure Blob Storage Hot/Cool access tier
* Amazon S3 Standard storage class
* Amazon S3 Standard-Infrequent Access storage class
* Amazon S3 One Zone-Infrequent Access storage class
* Amazon S3 Glacier Instant Retrieval storage class
* S3 Compatible object storage repository

For more information, see [Exploring Backup Copies](vbo_exploring_backup_copies.md) and [Data Restore](vbo_data_restore.md).

|  |
| --- |
| Note |
| You cannot explore and restore both the retrieved backed-up data and backup copies using Restore Portal. |

Page updated 9/2/2024

Page content applies to build 8.3.0.2201
