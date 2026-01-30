---
title: "Stopping Backup Job"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/stopping_backup_job.html"
last_updated: "9/2/2024"
product_version: "8.3.0.2201"
---

# Stopping Backup Job


When Veeam Backup for Microsoft 365 stops a backup job, it preserves the data that has already been backed up. If you want to continue, use the Start command. For more information, see [Starting Backup Job](starting_backup_job.md).

Keep in mind that when you restart the backup job, Veeam Backup for Microsoft 365 starts data processing from the beginning and may need additional time to re-identify the state of the backed-up data. After that Veeam Backup for Microsoft 365 continues with the remaining data to back up.

To stop a backup job, do the following:

1. Open the Organizations view.
2. In the inventory pane, select an organization.

|  |
| --- |
| Tip |
| You can also select the root Organizations node to see all backup and backup copy jobs that were created for all organizations added to the scope. |

1. In the preview pane, do one of the following:

* Select a backup job and click Stop on the ribbon.

* Right-click a backup job and select Stop.

[![Stopping Backup Job](images/stop_bj.webp)](images/stop_bj.webp "Stopping Backup Job")


