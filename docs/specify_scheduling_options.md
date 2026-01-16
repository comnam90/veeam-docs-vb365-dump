---
title: "specify_scheduling_options"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/specify_scheduling_options.html"
last_updated: "11/12/2025"
product_version: "8.3.0.2201"
---


In this article

At this step of the wizard, configure a schedule for your backup job and actions that will be performed after completion of the wizard.

To configure a schedule, do the following:

1. If you want Veeam Backup for Microsoft 365 to run your backup job automatically in accordance with the schedule, select the Run the job automatically check box and customize a schedule. You can select one of the following options:

* Daily at this time. Select this option if you want to run the job on the specified days at the specified hours. Keep in mind that the Workdays option means that Veeam Backup for Microsoft 365 will run the job every day from Monday to Friday at the specified time.

|  |
| --- |
| Note |
| When you configure the job schedule, keep in mind possible date and time changes (for example, related to daylight saving time transition). |

* Periodically every. Select this option if you want to run the job every N minutes or hours. If you select the period in hours, click Schedule and specify allowed and prohibited hours for the backup job to run. For more information, see [Selecting Time Periods](#stp).

1. Select the Retry failed objects processing check box and specify the maximum number of retry attempts. You can also set an interval between subsequent retries.
2. Select the Terminate the job if it exceeds allowed backup window check box, click Window and specify allowed and prohibited hours for the backup job. For more information, see [Selecting Time Periods](#stp).
3. In the When I click Create section, do the following:

1. Select the Start the job check box if you want to start a backup job right after completion of the wizard.

If you do not want to start the job immediately, you can start it later. For more information, see [Starting Backup Job](starting_backup_job.md).

1. Select the Create a backup copy for this job check box if you want to configure creating backup copies.

Right after you click Create, you will be taken to the [Select Target Backup Repository](target_backup_copy_repo.md) step of the New Backup Copy Job wizard.

Keep in mind that this check box is available only if the following conditions are met:

* You have specified an [object storage repository](specify_backup_proxy_server.md) to store your backups.
* You have added at least one more object storage repository to the Veeam Backup for Microsoft 365 backup infrastructure. For more information, see [Object Storage Repositories](vbo_osr.md#usage_scenarios) and [Backup Copy](vbo_backup_copy.md).

If you do not want to configure a backup copy job immediately, you can launch the New Backup Copy Job wizard later. For more information, see [Launch New Backup Copy Job Wizard](launch_new_backup_copy_job_wizard.md).

[![Specifying Scheduling Options](images/bu_job_schedule.webp)](images/bu_job_schedule.webp "Specifying Scheduling Options")

Selecting Time Periods

When you click Schedule or Window, the Time Periods dialog appears in which you can:

* Set the Permitted execution time frame for the backup job.
* Set the Denied execution time frame for the backup job.
* [In the Schedule window only] Specify a number of minutes for which you want to shift starting of the backup job within an hour if several backup jobs are scheduled to be started simultaneously. Using this option allows you to decrease the load on the Veeam Backup for Microsoft 365 backup infrastructure.

The main area of the dialog is divided into two axes:

* The vertical axis represents days of the week from Sunday to Saturday.
* The horizontal axis represents time intervals from 12 AM to 11:59 PM.

Within these axes a matrix is placed consisting of blocks. Each block represents a 59 minutes interval for each day of the week. The total number of blocks is 168 (24 blocks per each day of the week).

To set up an execution frame for the backup job, do the following:

1. Select a block that corresponds to the day of the week (vertical axis) and to the time interval (horizontal axis) on which you want to allow or prohibit the execution of a backup job.

In addition, you can:

1. Select multiple blocks simultaneously by clicking and holding the mouse pointer on the first block and dragging it until the last one that you want to use, including different days of the week.
2. Click a day of the week in the vertical axis to select all the blocks of the day.
3. Click All in the vertical axis to select all the blocks of the entire week.

1. On the right-hand side, select either the Permitted or Denied option to set up the execution rule for the selected blocks.

The following is an example in which it is prohibited to run a backup job on the following days of the week:

* Monday from 03:00 AM up until 09:59 AM.
* Thursday from 02:00 PM up until 08:59 PM.

[![Selecting Time Periods](images/time_intervals.webp)](images/time_intervals.webp "Selecting Time Periods")

Page updated 11/12/2025

Page content applies to build 8.3.0.2201
