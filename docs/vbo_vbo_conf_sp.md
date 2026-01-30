---
title: "Configuring Veeam Backup for Microsoft 365"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_vbo_conf_sp.html"
last_updated: "9/2/2024"
product_version: "8.3.0.2201"
---

# Configuring Veeam Backup for Microsoft 365


To configure Veeam Backup for Microsoft 365 on a service provider side, the following actions must be performed:

1. Configure the Veeam Backup for Microsoft 365 environment. For more information on how to configure Veeam Backup for Microsoft 365 settings, see [General Settings](vbo_general_application_settings.md).
2. Enable tenant authentication to the Veeam Backup for Microsoft 365 server to perform self-restore procedures. For more information, see [Authentication Settings](vbo_authentication_settings.md#tenants).
3. Configure backup proxy servers. For more information, see [Backup Proxy Servers](vbo_backup_proxy_servers.md).
4. Configure backup repositories. For more information, see [Backup Repositories](vbo_backup_repositories.md).
5. Add tenant organizations to the Veeam Backup for Microsoft 365 scope. For more information, see [Organization Management](vbo_managing_organizations.md).
6. Configure backup and backup copy for data in tenant organizations. For more information, see [Data Backup](vbo_data_backup.md) and [Backup Copy](vbo_backup_copy.md).
7. Configure data restore using Restore Portal for end users and restore operators from tenant organizations. For more information, see [Configuring Restore Portal for Multiple Tenants](ssp_configuration.md#multiple_tenants).

|  |
| --- |
| Note |
| As a service provider, you must obtain Microsoft organization credentials of your tenants. The same credentials will be used by tenants to connect to the Veeam Backup for Microsoft 365 server on a service provider side for self-restore procedures using Veeam Explorers. |


