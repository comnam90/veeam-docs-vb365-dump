---
title: "Rental License"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_rental_license.html"
last_updated: "9/9/2025"
product_version: "8.3.0.2201"
---

# Rental License


Rental License is a paid and fully-functional license that expires at the end of the contract. The rental license term is normally 1 month from the contract start date. The license expiration date is the last day of the month. This license type is distributed only to service providers.

In contrast to Subscription license, Rental license is available only in the M365 license package. For Veeam Backup for Microsoft 365 with this type of license, Veeam ONE monitoring is available if Veeam ONE also has Rental license.

For more information on the compatibility of Veeam Backup for Microsoft 365 licenses with Veeam ONE licenses, see the [Compatibility with Veeam Backup for Microsoft 365 Licenses](https://helpcenter.veeam.com/docs/one/userguide/license_types.html?ver=13#compatibility-with-veeam-backup-for-microsoft-365-licenses) section of the Veeam ONE Deployment Guide and [this Veeam KB article](https://www.veeam.com/kb4422).

New User

When Veeam Backup for Microsoft 365 backs up a user account for the first time, such user account obtains the new user status until the first day of the following month. During this period, user accounts with the new user status do not consume the rental license units.

For example, you want to back up three user accounts A, B and C and the first session of a backup job is scheduled on January 13, 2024. After the backup session, these user accounts will be given the new user status until February 1, 2024. On February 1, 2024, the new user status for each of these accounts will be automatically reset. After the new user status is reset, upon the next backup job session these user accounts start consuming the rental license immediately.

You can avoid consuming the rental license by user accounts with the new user status that you no longer want to process. For example, you may not want to continue backing up the user account B. To do this, remove this account from the backup job processing list before Veeam Backup for Microsoft 365 resets automatically the new user status for this account. Starting from the following month, user accounts A and C will start consuming the rental license, but the user account B will not.

License Expired

For purpose of renewal, Veeam Backup for Microsoft 365 grants a grace period of 2 months after the license expiration. During this period, the product functionality is not limited. After this period, Veeam Backup for Microsoft 365 stops processing all user accounts in all organizations and terminates all scheduled jobs with failure. Veeam Backup for Microsoft 365 sends you a notification message to inform you that the license is either about to expire or has expired.

The restore abilities will continue to function regardless of whether your license has expired or not.

License Exceeded

Additional processing of no more than 20 user accounts or 20% of the license count (whichever is greater) is granted if you exceed the license limit.

Veeam Backup for Microsoft 365 doubles grace limit after the following conditions are met:

* You selected the Update license automatically check box in the License Information window. For more information, see [Installing and Updating License](vbo_installing_license.md).
* At least one usage report has been successfully sent from the Veeam Backup for Microsoft 365 server to Veeam during the last month. Veeam Backup for Microsoft 365 sends this report automatically.

As a result, Veeam Backup for Microsoft 365 allows you to exceed the license limit by up to 40 user accounts or up to 40% of the license count (whichever is greater).

Extra user accounts that go beyond the exceeded license limit are not processed. Veeam Backup for Microsoft 365 displays a warning message to notify you that the license limit is exceeded.

Veeam Backup for Microsoft 365 allows you to process extra user accounts according to the FIFO queue logic (that is, "first in — first out"). Extra accounts are queued for processing. Once the unconsumed license unit appears, the first extra user account from the queue obtains this license unit and will be backed up.

The grace period is 2 months. After this period, Veeam Backup for Microsoft 365 stops processing excessive user accounts (in FIFO queue); no more extra accounts will be queued for processing.

The restore abilities will continue to function regardless of exceeding the grace limit and the grace period state.

In This Section

[Managing Monthly Usage Report](vbo_monthly_usage_report.md)


