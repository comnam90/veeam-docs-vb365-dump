---
title: "Permissions for Modern Authentication and Legacy Protocols"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/ad_app_permissions_legacy.html"
last_updated: "8/22/2024"
product_version: "8.3.0.2201"
---

# Permissions for Modern Authentication and Legacy Protocols


Since [Microsoft deprecated basic authentication and legacy authentication protocols](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-september/ba-p/3609437), you cannot add new Microsoft 365 organizations to Veeam Backup for Microsoft 365 using modern authentication method with legacy protocols allowed. However, you can continue to use Veeam Backup for Microsoft 365 to [back up](vbo_data_backup.md) and [restore](vbo_data_restore.md) data of Microsoft 365 organizations that were added to previous installations of the product using this authentication method.

The following table lists permissions that must be granted to Microsoft Entra applications to perform a backup for Microsoft 365 organizations with modern authentication and legacy protocols.

All listed permissions are of the Application type and required for data backup.

| API | Permission name | Exchange Online | SharePoint Online and OneDrive for Business | Microsoft Teams | Description |
| --- | --- | --- | --- | --- | --- |
| Microsoft Graph | Directory.Read.All | ✔ | ✔ | ✔ | Querying Microsoft Entra ID for organization properties, the list of users and groups and their properties. |
| Group.Read.All | ✔ | ✔ | ✔ | Querying Microsoft Entra ID for the list of groups and group sites. |
| TeamSettings.ReadWrite.All |  |  | ✔ | Accessing archived teams. |
| Sites.Read.All |  | ✔ |  | Accessing sites of the applications that are installed from the SharePoint store. |
| Office 365 Exchange Online | full\_access\_as\_app | ✔ |  | ✔ | Reading mailboxes content. |
| Office 365 SharePoint Online | Sites.FullControl.All |  | ✔ | ✔ | Reading SharePoint sites and OneDrive accounts content. |
| User.Read.All |  | ✔ | ✔ | Reading OneDrive accounts (getting site IDs). |


