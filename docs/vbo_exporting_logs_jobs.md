---
title: "vbo_exporting_logs_jobs"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_exporting_logs_jobs.html"
last_updated: "9/9/2025"
product_version: "8.3.0.2201"
---


In this article

To collect log files for backup and backup copy jobs, do the following:

1. In the main menu, click Help and Support > Support information.
2. Select the Collect logs option.

[![Collecting Log Files](images/send_logs_00.webp)](images/send_logs_00.webp "Collecting Log Files")

1. Select the Collect logs for selected jobs option.

[![Collecting Log Files](images/logs_jobs.webp)](images/logs_jobs.webp "Collecting Log Files")

1. Select backup and backup copy jobs for which to obtain log files. Logs will be collected for the selected jobs and for all backup proxy servers involved in the processing of these jobs. Additionally, Veeam Backup for Microsoft 365 collects information about general settings of the product and the backup infrastructure components, as well as Veeam Backup for Microsoft 365 license details.

[![Collecting Log Files](images/logs_select_jobs.webp)](images/logs_select_jobs.webp "Collecting Log Files")

1. Specify a time period for log export:

* Select the Collect logs for the last N days option to specify the number of days for which to export your log files.
* Select the Collect logs for the specified time period option to set up a period for log files export.
* Select the Collect all logs option to export all existing log files regardless of the time period.

[![Collecting Log Files](images/send_logs_2.webp)](images/send_logs_2.webp "Collecting Log Files")

1. Specify the path.

[![Collecting Log Files](images/send_logs_3.webp)](images/send_logs_3.webp "Collecting Log Files")

1. Click Finish.

Once log files are collected, Veeam Backup for Microsoft 365 prompts you to view logs collection statistics by expanding the Export Logs dialog. You can open a folder where log files were exported. To do this, click Open folder.

[![Viewing Summary](images/export_logs_jobs_summary.webp)](images/export_logs_jobs_summary.webp "Viewing Summary")

Page updated 9/9/2025

Page content applies to build 8.3.0.2201
