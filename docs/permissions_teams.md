---
title: "permissions_teams"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/permissions_teams.html"
last_updated: "7/5/2024"
product_version: "8.3.0.2201"
---


In this article

To back up Microsoft Teams data, Veeam Backup for Microsoft 365 requires access to the Exchange mailbox of the group associated with a team and to the SharePoint site of this group. Thus, for Microsoft 365 organizations that use modern authentication method with legacy protocols allowed or basic authentication method, Veeam Backup account must have permissions required for backup of Exchange Online and SharePoint Online data. For more information, see [Microsoft Exchange](permissions_exchange.md) and [Microsoft SharePoint and OneDrive for Business](permissions_sharepoint.md).

In addition, Veeam Backup account must meet the following requirements:

* The account must have a Microsoft 365 license that permits access to Microsoft Teams APIs. The minimum sufficient license is Microsoft Teams Exploratory experience. For more information about the Microsoft Teams Exploratory experience, see [this Microsoft article](https://learn.microsoft.com/en-us/microsoftteams/teams-exploratory).
* The account must have the Team Administrator role assigned.

|  |
| --- |
| Note |
| Consider the following:   * For Microsoft 365 organizations that use modern authentication method with legacy protocols allowed, and in case you specify different accounts to connect to Microsoft Exchange and Microsoft SharePoint, the required license and role must be assigned to the account used to connect to Microsoft SharePoint. * When you back up Microsoft Teams data in an organization that uses the basic authentication method, Veeam Backup for Microsoft 365 adds a service account to every team and then removes it. * For more information about permissions required to restore Microsoft Teams data from backups created by Veeam Backup for Microsoft 365, see [Permissions](https://helpcenter.veeam.com/docs/vbo365/explorers/vet_permissions.html?ver=80) for Veeam Explorer for Microsoft Teams. |

Page updated 7/5/2024

Page content applies to build 8.3.0.2201
