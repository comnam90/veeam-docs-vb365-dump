---
title: "how_backup_copy_works"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/how_backup_copy_works.html"
last_updated: "6/3/2025"
product_version: "8.3.0.2201"
---


In this article

As well as the backup process, backup copy is conducted by a [backup proxy server](vbo_backup_proxy_servers.md) or a [backup proxy pool](vbo_proxy_pools.md). To speed up the backup copy process and reduce costs incurred by your cloud storage provider, you can enable usage of the Amazon or Azure archiver appliance. This option can be configured when creating an object storage repository in Veeam Backup for Microsoft 365 or editing its settings. The type of the created appliance depends on the object storage repository vendor. For more information, see [Configuring Amazon Archiver Appliance](new_amazon_s3_backup_proxy.md#appliance), [Configuring Azure Archiver Appliance](new_azure_backup_proxy.md#appliance), and [Editing Object Storage Repository Settings](vbo_editing_repository.md#osr).

Consider the following:

* Both source and target backup repositories for backup copy must be object storage repositories. They must be associated with the same backup proxy server or backup proxy pool and have the same retention type.
* Object storage repository that you selected as a target for your backup job becomes a source backup repository for backup copies. A target object storage repository to store backup copies must be specified when you configure a backup copy job. For more information, see [Creating Backup Copy Job](vbo_new_copy_job.md).

Veeam Backup for Microsoft 365 performs backup copy in the following way:

1. The backup proxy server establishes a connection with a source object storage repository for backup copies.
2. The backup proxy server accesses data blobs that belong to the latest restore point that appeared in the source object storage repository since the backup copy job was created.
3. The backup proxy server or, if configured, the archiver appliance repacks the backed-up data, creating larger blob files. Processing larger blobs helps you reduce costs incurred by your cloud storage provider for retrieving backed-up data from backup copies.
4. The backup proxy server compresses data blobs and encrypts them, if necessary. For more information, see [Compression](understanding_compression.md) and [Data Encryption](data_encryption.md).
5. The backup proxy server transfers data blobs to a target object storage repository for long-term storage. For more information about Amazon S3 storage classes and Azure storage account types that Veeam Backup for Microsoft 365 supports, see [Supported Amazon S3 Storage Classes](supported_storage_classes_amazon.md) and [Supported Azure Storage Account Types](supported_storage_account_types.md).

Related Topics

[Getting Started with Backup Copy](get_started_backup_copy.md)

Page updated 6/3/2025

Page content applies to build 8.3.0.2201
