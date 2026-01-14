---
title: "vbo_licensing"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_licensing.html"
last_updated: "1/22/2025"
product_version: "8.3.0.2201"
---


In this article

Licensing in Veeam Backup for Microsoft 365 is based on user accounts whose data you back up. Each protected user account consumes one Veeam license unit.

|  |
| --- |
| Note |
| Veeam Backup for Microsoft 365 consumes license units only to back up data, restore does not require licenses. |

The Veeam license units are consumed by the following objects included to a user account:

* Microsoft Exchange Online and on-premises Microsoft Exchange mailboxes

Such a mailbox can be a personal mailbox, an Online Archive mailbox or both — you will only need one Veeam license unit per object.

* Microsoft OneDrive for Business account

Consider that OneDrive (without for Business) is an independent storage service and is not supported by Veeam Backup for Microsoft 365.

* Microsoft SharePoint Online and on-premises Microsoft SharePoint personal sites

A personal SharePoint site of a licensed user consumes one Veeam license unit.

The Veeam license units are consumed by mailboxes, OneDrive for Business accounts and SharePoint personal sites for which at least one restore point has been created within the last 31 days. If an object was not backed up for 31 days, its license unit is automatically revoked.

|  |
| --- |
| Note |
| When you plan a number of units in your Veeam license, consider the following:   * All users in your Microsoft 365 subscription or on-premises deployment that are members of a backed-up team or have access to a backed-up team, communication, collaboration and other non-personal SharePoint sites must be licensed. If you have a hybrid SharePoint deployment (on-premises Microsoft SharePoint and SharePoint Online), and the same user has access to both, then only one Veeam license is required. * If you back up only Microsoft Teams objects or non-personal SharePoint sites, the Veeam license units are not consumed by Veeam Backup for Microsoft 365. |

The following objects do not require the Veeam license and do not consume units from it:

* Microsoft Teams objects

These objects do not consume units from the Veeam license.

* Group and non-personal SharePoint sites

These sites do not consume units from the Veeam license.

* Shared, resource, group and public folder mailboxes

These mailboxes do not consume units from the Veeam license if such mailboxes do not have a Microsoft 365 license assigned.

* External SharePoint users

An external SharePoint user is a user from outside your Microsoft 365 subscription who has access to one or more sites, files or folders. External authenticated users are limited to basic collaboration tasks, and external anonymous users can edit or view specific documents if they have specific permissions.

* Guest Microsoft Teams users

A guest team user is a user from outside your Microsoft 365 subscription who has access to a backed-up team.

|  |
| --- |
| Note |
| For more information on Microsoft licenses required to back up user mailboxes, public folder mailboxes, SharePoint and OneDrive for Business objects, see [Considerations and Limitations](vbo_considerations.md#bp). |

License Types

Veeam Backup for Microsoft 365 supports the following types of licenses:

* [Subscription License](vbo_subscription_license.md)

Paid, fully-functional license that expires at the end of the subscription term. The subscription license term is normally 1–5 years from the contract start date (depending on the subscription length).

* [Rental License](vbo_rental_license.md)

Paid, fully-functional license that expires at the end of the contract. The rental license term is normally 1 month from the contract start date. The license expiration date is the last day of the month. This license type is distributed only to service providers.

* [Not For Resale License](vbo_nfr_license.md)

Free, fully-functional license that can be used for product demonstration, training and education. This license is not for resale or other commercial use.

* [Evaluation License](vbo_evaluation_license.md)

Free, fully-functional license that can be used for evaluation and testing purposes only.

|  |
| --- |
| Note |
| During the Veeam Backup for Microsoft 365 installation or after you install the product, you will be prompted to provide a license. You can dismiss this step and continue using the product without any [license installed](vbo_installing_license.md). In this case, the product will operate in the Community Edition mode that allows you to process up to 10 user accounts, up to 1 TB of Microsoft SharePoint data and up to 10 teams in all organizations. Community Edition mode is not limited in time and does not have limitations in terms of the product functionality. |

Page updated 1/22/2025

Page content applies to build 8.3.0.2201
