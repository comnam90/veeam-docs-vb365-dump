---
title: "vbo_maintenance_creds_disable"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_maintenance_creds_disable.html"
last_updated: "7/17/2024"
product_version: "8.3.0.2201"
---


In this article

This step is available if you have selected Windows-based backup proxy server at the [Select Backup Proxy Server](vbo_selecting_proxy_server_maintenance_disable.md) step of the wizard.

At this step of the wizard, enter user credentials to connect to the backup proxy server.

|  |
| --- |
| Note |
| Consider the following:   * The account must be a member of the local Administrators group. * If you want to disable the maintenance mode for multiple Windows-based backup proxy servers, you must specify a user account that Veeam Backup for Microsoft 365 can use to connect to all selected Windows-based backup proxy servers. |

To do this, select one of the following options:

* Use current account. Select this option to connect to the backup proxy server using credentials under which you are currently logged in.
* Use the following account. Select this option to connect to the backup proxy server using credentials that you must specify in the Username and Password fields.

[![Disabling Maintenance Mode](images/proxy_pool_maintenance_creds.webp)](images/proxy_pool_maintenance_creds.webp "Disabling Maintenance Mode")

Page updated 7/17/2024

Page content applies to build 8.3.0.2201
