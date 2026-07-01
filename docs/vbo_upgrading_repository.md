---
title: "Upgrading Backup Repositories"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_upgrading_repository.html"
last_updated: "5/15/2026"
product_version: "8.5.0.1014"
---

# Upgrading Backup Repositories


If a backup repository configured in your environment is marked as Out of Date, it must be upgraded manually.

|  |
| --- |
| Note |
| If you upgraded Veeam Backup for Microsoft 365 to 8.5, all backup repositories configured in your environment will be upgraded automatically right after upgrading backup proxy servers. For more information, see [Upgrading Backup Proxy Servers](vbo_upgrading_proxy_server.md). |

To upgrade a backup repository, do the following:

1. Open the Backup Infrastructure view.
2. In the inventory pane, select the Backup Repositories > Out of Date node.
3. In the preview pane, do one of the following:

* Select a backup repository and click Upgrade Repository on the ribbon.

* Right-click a backup repository and select Upgrade.

If you want to stop upgrade, click Stop Upgrade on the ribbon.

[![Upgrading Backup Repositories](images/upgrade_backup_repositories.webp)](images/upgrade_backup_repositories.webp "Upgrading Backup Repositories")

Related Topics

[Indexing Backup Repositories](indexing.md)


