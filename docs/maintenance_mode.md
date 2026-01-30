---
title: "Maintenance Mode"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/maintenance_mode.html"
last_updated: "8/27/2024"
product_version: "8.3.0.2201"
---

# Maintenance Mode


If you want to perform service operations, you can put backup proxy servers added to a backup proxy pool in the maintenance mode. Veeam Backup for Microsoft 365 will not interrupt backup operations that are currently executed on this backup proxy pool. Putting a backup proxy server under maintenance means that Veeam Backup for Microsoft 365 disables Veeam Backup for Microsoft 365 Proxy Service on this backup proxy server. When a backup proxy server is put under maintenance, Veeam Backup for Microsoft 365 re-assigns execution of backup operations to another active backup proxy server within the same backup proxy pool.

You can return backup proxy servers from maintenance if it is no longer needed. This means that Veeam Backup for Microsoft 365 enables Veeam Backup for Microsoft 365 Proxy Service on this backup proxy server.

In This Section

* [Putting Under Maintenance](backup_proxy_maintenance_enable.md)
* [Returning From Maintenance](backup_proxy_maintenance_disable.md)


