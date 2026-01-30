---
title: "Step 3. Specify Credentials"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_upgrade_creds.html"
last_updated: "7/17/2024"
product_version: "8.3.0.2201"
---

# Step 3. Specify Credentials


This step is available if you have selected to upgrade a Windows-based backup proxy server at the [Select Backup Proxy Server to Upgrade](vbo_selecting_proxy_server.md) step of the wizard.

At this step of the wizard, enter user credentials to connect to the backup proxy server.

|  |
| --- |
| Note |
| Consider the following:   * The account must be a member of the local Administrators group. * If you want to upgrade multiple Windows-based backup proxy servers, you must specify a user account that Veeam Backup for Microsoft 365 can use to connect to all selected Windows-based backup proxy servers. |

To do this, select one of the following options:

* Use current account. Select this option to connect to the backup proxy server using credentials under which you are currently logged in.
* Use the following account. Select this option to connect to the backup proxy server using credentials that you must specify in the Username and Password fields.

[![Upgrading Backup Proxy Servers](images/upgrading_proxy_3.webp)](images/upgrading_proxy_3.webp "Upgrading Backup Proxy Servers")


