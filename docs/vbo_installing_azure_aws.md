---
title: "Deploying to Microsoft Azure and AWS"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_installing_azure_aws.html"
last_updated: "11/11/2025"
product_version: "8.3.0.2201"
---

# Deploying to Microsoft Azure and AWS


To deploy Veeam Backup for Microsoft 365 to Microsoft Azure or Amazon Web Services (AWS) cloud platforms, do the following:

1. Install Veeam Backup for Microsoft 365 on a Microsoft Azure or AWS virtual machine. For more information, see [Installing Veeam Backup for Microsoft 365](vbo_installing_vbo.md).

When deploying to Microsoft Azure, you can use [F-Series VM Sizes](https://azure.microsoft.com/en-us/blog/f-series-vm-size/) for better performance. You can use only VM Sizes that meet [system requirements](vbo_system_requirements.md#ManagementServer).

1. Configure additional backup proxy servers. For more information, see [Backup Proxy Servers](vbo_backup_proxy_servers.md).

For more information on how to deploy a backup proxy server to AWS, see [this Veeam KB article](https://www.veeam.com/kb3212).

1. Configure backup proxy pools. For more information, see [Backup Proxy Pools](vbo_proxy_pools.md).
2. Configure backup repositories. For more information, see [Backup Repositories](vbo_backup_repositories.md).

After deployment is complete, you can:

* Add Microsoft 365 and on-premises Microsoft organizations to the Veeam Backup for Microsoft 365 scope. For more information, see [Organization Management](vbo_managing_organizations.md).
* Create backups. For more information, see [Data Backup](vbo_data_backup.md).
* View and restore your data. For more information, see [Data Restore](vbo_data_restore.md).


