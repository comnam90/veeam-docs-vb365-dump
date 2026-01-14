---
title: "getting_started_vbo"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/getting_started_vbo.html"
last_updated: "9/3/2024"
product_version: "8.3.0.2201"
---


In this article

Before you start using Veeam Backup for Microsoft 365, you can check the following prerequisites:

* Become familiar with the Veeam Backup for Microsoft 365 architecture to carefully plan your backup infrastructure layout. For more information, see [Veeam Backup for Microsoft 365 Architecture](architecture.md).
* Make sure that machines on which you plan to deploy the Veeam Backup for Microsoft 365 components meet hardware recommendations and system requirements. For more information, see [System Requirements](vbo_system_requirements.md).
* Become familiar with the authentication options that Veeam Backup for Microsoft 365 requires. For more information about permissions in Veeam Backup for Microsoft 365, see [Permissions](vbo_required_permissions.md).

To use Veeam Backup for Microsoft 365, perform the following steps:

1. Deploy Veeam Backup for Microsoft 365. For more information, see [Deployment](vbo_deployment.md).
2. Launch Veeam Backup for Microsoft 365 Console. For more information, see [Launching Veeam Backup for Microsoft 365](vbo_application_launch.md).
3. Configure general settings of Veeam Backup for Microsoft 365. For more information, see [General Settings](vbo_general_application_settings.md).

This step is optional. You can use Veeam Backup for Microsoft 365 with the default settings, or, for example, configure REST API and Restore Portal if you plan to use these product components.

1. Configure backup infrastructure. You can configure the following backup infrastructure components:

* Backup proxy servers

By default, Veeam Backup for Microsoft 365 runs with the default backup proxy server hosted on the same machine where the product is installed. You can add additional backup proxy servers to distribute backup traffic among these backup proxy servers. For more information, see [Backup Proxy Servers](vbo_backup_proxy_servers.md).

* Backup proxy pools

This step is optional. By default, Veeam Backup for Microsoft 365 runs without preconfigured backup proxy pools. A backup proxy pool is a logical entity that you configure to group several backup proxy servers. Using backup proxy pools provides better scalability and load balancing. For more information, see [Backup Proxy Pools](vbo_proxy_pools.md).

* Backup repositories

By default, Veeam Backup for Microsoft 365 uses the default backup repository located on the same machine where the product is installed. You can add additional JET-based backup repositories and object storage repositories to store backups in different locations for enhanced protection. If you add object storage repositories, you can stores backups and backup copies in supported cloud or on-premises storage systems. For more information, see [Backup Repositories](vbo_backup_repositories.md).

1. Add a Microsoft organization whose data you want to protect. For more information, see [Organization Management](vbo_managing_organizations.md).
2. Create a backup job. You can create different backup jobs with different objects added to a backup job scope and map backup jobs to different backup repositories. For more information, see [Data Backup](vbo_data_backup.md).
3. Create a backup copy job to transfer backups created by a source backup job to an object storage repository for long-term storage.

This step is optional. You can create a backup copy job right after configuring a backup job or at any time later. For more information, see [Backup Copy](vbo_backup_copy.md).

1. Whenever you need, explore and restore backed-up data of your Microsoft organizations. For more information, see [Data Restore](vbo_data_restore.md).

Page updated 9/3/2024

Page content applies to build 8.3.0.2201
