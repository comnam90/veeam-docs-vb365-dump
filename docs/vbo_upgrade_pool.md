---
title: "vbo_upgrade_pool"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_upgrade_pool.html"
last_updated: "12/10/2024"
product_version: "8.3.0.2201"
---


In this article

When you upgrade Veeam Backup for Microsoft 365 to a newer version, Veeam Backup for Microsoft 365 does not interrupt backup operations that are currently executed on backup proxy pools. However, Veeam Backup for Microsoft 365 needs to upgrade backup proxy pools as well — that is, to elevate the backup proxy pool version. To work properly, backup proxy pools and the Veeam Backup for Microsoft 365 controller must have the same version.

Consider the following:

* The backup proxy pool continues to handle backup operations, even if it includes a mix of already upgraded and non-upgraded backup proxy servers. The upgraded backup proxy servers will remain Inactive until all other backup proxy servers in the same backup proxy pool have also been upgraded.
* Backup proxy pool upgrade is performed by the Veeam Backup for Microsoft 365 controller only when all backup proxy servers in the same backup proxy pool are upgraded: Veeam Backup for Microsoft 365 elevates the backup proxy pool version and changes the status of the upgraded backup proxy servers from Inactive to Active.
* The current version of the backup proxy pool is not displayed in the Veeam Backup for Microsoft 365 console.
* Veeam Backup for Microsoft 365 ignores backup proxy servers that are currently under maintenance.

Related Topics

[Upgrading Backup Proxy Servers](vbo_upgrading_proxy_server.md)

Page updated 12/10/2024

Page content applies to build 8.3.0.2201
