---
title: "Exploring Backup Jobs"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_exploring_backup_jobs.html"
last_updated: "9/2/2024"
product_version: "8.3.0.2201"
---

# Exploring Backup Jobs


When exploring backup jobs, Veeam Backup for Microsoft 365 loads the latest restore point that was created by the selected job.

The following is an example of exploring the Backup Job 2 from the Repository 2. This job has three restore points created on January 20, January 27 and February 4. In such a scenario, Veeam Backup for Microsoft 365 loads only the latest restore point (created on February 4) into the Veeam Explorers scope.

[![Exploring Veeam Backup for Microsoft Office 365 Backups](images/explore_backup_1_bj_scheme.webp)](images/explore_backup_1_bj_scheme.webp "Exploring Veeam Backup for Microsoft Office 365 Backups")

To open backups created by the selected backup job, do the following:

1. Open the Organizations view.
2. In the inventory pane, select an organization.
3. In the preview pane, select a backup job that contains backups that you want to open.
4. On the Jobs tab, click Explore, or right-click a backup job and select one of the following options:

* Explore latest <product> state of <date\_and\_time>. To explore the latest backup state.
* Explore <product> point-in-time state. To select a point-in-time state. For more information, see [Exploring Point In Time](vbo_exploring_point_in_time.md).

where <product> is one of the following services: Exchange, SharePoint, OneDrive, or Teams.

[![Exploring Backup Job](images/explore_backup_1.webp)](images/explore_backup_1.webp "Exploring Backup Job")


