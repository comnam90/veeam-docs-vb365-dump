---
title: "Subscription License"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_subscription_license.html"
last_updated: "9/9/2025"
product_version: "8.3.0.2201"
---

# Subscription License


Subscription License is a paid and fully-functional license that expires at the end of the subscription term. The subscription license term is normally 1–5 years from the contract start date (depending on the subscription length).

Subscription license is available in the M365 and M365Suite license packages. Veeam ONE monitoring is available if the M365Suite license package is installed.

For more information on the compatibility of Veeam Backup for Microsoft 365 licenses with Veeam ONE licenses, see the [Compatibility with Veeam Backup for Microsoft 365 Licenses](https://helpcenter.veeam.com/docs/one/userguide/license_types.html?ver=13#compatibility-with-veeam-backup-for-microsoft-365-licenses) section of the Veeam ONE Deployment Guide and [this Veeam KB article](https://www.veeam.com/kb4422).

License Expired

For purpose of renewal, Veeam Backup for Microsoft 365 grants a grace period of 1 month after the license expiration. During this period, the product functionality is not limited. After this period, Veeam Backup for Microsoft 365 stops processing all user accounts in all organizations and terminates all scheduled jobs with failure. Veeam Backup for Microsoft 365 sends you a notification message to inform you that the license is either about to expire or has expired.

The restore abilities will continue to function regardless of whether your license has expired or not.

License Exceeded

Additional processing of no more than 10 user accounts or 10% of the license count (whichever is greater) is granted if you exceed the license limit.

Veeam Backup for Microsoft 365 doubles grace limit after the following conditions are met:

* You selected the Update license automatically check box in the License Information window. For more information, see [Installing and Updating License](vbo_installing_license.md).
* At least one usage report has been successfully sent from the Veeam Backup for Microsoft 365 server to Veeam during the last month. Veeam Backup for Microsoft 365 sends this report automatically.

As a result, Veeam Backup for Microsoft 365 allows you to exceed the license limit by up to 20 user accounts or up to 20% of the license count (whichever is greater).

Extra user accounts that go beyond the exceeded license limit are not processed. Veeam Backup for Microsoft 365 displays a warning message to notify you that the license limit is exceeded.

Veeam Backup for Microsoft 365 allows you to process extra user accounts according to the FIFO queue logic (that is, "first in — first out"). Extra accounts are queued for processing. Once the unconsumed license unit appears, the first extra user account from the queue obtains this license unit and will be backed up.

The grace period is not limited and lasts during the whole term of the subscription.


