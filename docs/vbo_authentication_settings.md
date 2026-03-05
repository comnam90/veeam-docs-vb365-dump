---
title: "Authentication Settings"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_authentication_settings.html"
last_updated: "3/3/2026"
product_version: "8.3.0.2201"
---

# Authentication Settings


You can configure authentication settings to the Veeam Backup for Microsoft 365 server for tenants and restore operators.

Authentication to the Veeam Backup for Microsoft 365 server is required for them to connect to Veeam Backup for Microsoft 365 and perform restore operations within the following usage scenarios:

* Backup as a Service with Veeam Backup for Microsoft 365. In this scenario, tenants authenticate to Veeam Backup for Microsoft 365 server with Microsoft organization credentials.

Enabling tenant authentication is required for users from tenant organizations to view and restore backups that are located on the service provider side. For more information, see [Enabling Tenant Authentication](vbo_authentication_settings_tenants.md).

* Operator restore. In this scenario, restore operators authenticate to Veeam Backup for Microsoft 365 with their Microsoft 365 credentials. Restore operators use Restore Portal to view and restore data from backups created by Veeam Backup for Microsoft 365 for other users, groups, sites, teams or the entire Microsoft 365 organization.

Enabling restore operator authentication is required if you want to configure Restore Portal. For more information, see [Enabling Restore Operator Authentication](vbo_authentication_settings_restore_operators.md).

|  |
| --- |
| Note |
| To configure access to Veeam Backup for Microsoft 365 for users and restore operators from multiple tenant organizations, you must enable both options. |

Related Topics

* [Restore Portal Settings](vbo_restore_portal_settings.md)
* [Configuring REST API and Restore Portal on Separate Machine](vbo_configuring_rest_separate.md)
* [Backup as Service with Veeam Backup for Microsoft 365](vbo_mail_baas.md)
* [Data Restore Using Restore Portal](ssp_restore.md)


