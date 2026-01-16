---
title: "vbo_automatic_update"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_automatic_update.html"
last_updated: "7/11/2024"
product_version: "8.3.0.2201"
---


In this article

By default, Veeam Backup for Microsoft 365 automatically checks Veeam servers for critical updates once a day. If a new critical update is available, Veeam Backup for Microsoft 365 downloads this update in the background and installs it to the following backup infrastructure components:

* Veeam Backup for Microsoft 365 server

This target is used to update Veeam Backup for Microsoft 365, Veeam Explorers, PowerShell, and REST API.

* Remote backup proxy servers

|  |
| --- |
| Important |
| Automatic update is not supported for the Veeam Backup for Microsoft 365 REST API component installed on a separate machine and Veeam Explorers installed on a server with Veeam Backup & Replication for tenants. |

Veeam Backup for Microsoft 365 updates the backup infrastructure components in the following order:

1. Veeam Backup for Microsoft 365 server (including the local backup proxy).

Update is performed within the update window that is a period of the Veeam Backup for Microsoft 365 server idleness. The following conditions must be met:

* Restore sessions are not running on the Veeam Backup for Microsoft 365 server.
* The Veeam Backup for Microsoft 365 console and PowerShell console are closed. Otherwise, you will be prompted to close these consoles.
* Backup, backup copy and retrieval jobs as well as data management jobs are not running on the local backup proxy.

1. Veeam Explores, remote Veeam Backup for Microsoft 365 Console and PowerShell components.

Veeam Backup for Microsoft 365 will update these components only after the Veeam Backup for Microsoft 365 server update finishes.

1. Remote backup proxy servers.

Update is performed within the different update window. Veeam Backup for Microsoft 365 determines a time period when backup, backup copy and retrieval jobs as well as data management jobs are not running on a backup proxy server.

Thus, automatic update of Veeam Backup for Microsoft 365 can only be performed when the load on the backup infrastructure components is minimal. If Veeam Backup for Microsoft 365 cannot determine the proper update window during the 3-day period, you will be prompted to install updates manually. For more information, see [Checking for Updates](vbo_checking_for_updates.md).

You can disable automatic update in the Veeam Backup for Microsoft 365 settings. To do this, clear the Allow for automatic silent updates check box on the Updates tab. For more information, see [New Versions and Automatic Updates](vbo_configuring_update.md).

Page updated 7/11/2024

Page content applies to build 8.3.0.2201
