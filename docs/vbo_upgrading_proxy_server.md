---
title: "vbo_upgrading_proxy_server"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_upgrading_proxy_server.html"
last_updated: "12/10/2024"
product_version: "8.3.0.2201"
---


In this article

To communicate with backup proxy servers, Veeam Backup for Microsoft 365 uses the proprietary service — Veeam Backup for Microsoft 365 Proxy Service that is installed on the target proxy machine. When you upgrade Veeam Backup for Microsoft 365 to a newer version, this service becomes outdated and all backup proxy servers configured in your environment are marked as Out of Date and must be upgraded manually.

Before you start upgrading backup proxy servers, check whether the target proxy machine meets the system requirements. For more information, see [System Requirements](vbo_system_requirements.md#BackupProxy).

|  |
| --- |
| Note |
| Microsoft .NET and Windows PowerShell must be installed on the Windows-based backup proxy server in advance. |

If you need to upgrade a backup proxy server that is part of a backup proxy pool, consider the following:

* Before you begin the upgrade, the backup proxy server is marked as Out of Date but is still Active and handling all backup operations.
* Once the upgrade is complete, the upgraded backup proxy server will remain Inactive until all other backup proxy servers in the same backup proxy pool have also been upgraded.

For more information, see [Backup Proxy Pool Upgrade](vbo_upgrade_pool.md).

To upgrade backup proxy servers, do the following:

1. [Launch the Proxy Upgrade wizard](launch_new_proxy_upgrade_wizard.md).
2. [Select a backup proxy server to upgrade](vbo_selecting_proxy_server.md).
3. [Specify credentials](vbo_upgrade_creds.md).
4. [Specify the SSH connection settings](vbo_upgrade_ssh.md).
5. [Review the operation summary](vbo_upgrade_proxies_summary.md).

Page updated 12/10/2024

Page content applies to build 8.3.0.2201
