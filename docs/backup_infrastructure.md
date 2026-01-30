---
title: "Backup Infrastructure"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/backup_infrastructure.html"
last_updated: "9/3/2024"
product_version: "8.3.0.2201"
---

# Backup Infrastructure


The backup infrastructure of Veeam Backup for Microsoft 365 consists of the following:

* [Backup proxy servers](vbo_backup_proxy_servers.md)

Backup proxy servers are auxiliary machines that you configure to conduct all read and write activities, route backup traffic, handle data compression and encryption and send email notifications.

* [Backup proxy pools](vbo_proxy_pools.md)

Backup proxy pools are logical entities that you configure to group several backup proxy servers. Using backup proxy pools provides better scalability and load balancing.

* [Backup repositories](vbo_backup_repositories.md)

Backup repositories are storage systems within the backup infrastructure where Veeam Backup for Microsoft 365 saves backups and backup copies. Veeam Backup for Microsoft 365 allows you to save your data locally to a directory on a backup proxy server or to object storage repositories — cloud-based or on-premises storage systems that the product supports. For more information, see [JET-Based Backup Repositories](jet_backup_repo.md) and [Object Storage Repositories](vbo_osr.md).

Keep in mind that you can use Azure Blob Storage Archive access tier, Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes only as a target for backup copy jobs.


