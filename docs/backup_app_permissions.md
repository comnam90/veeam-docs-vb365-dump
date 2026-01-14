---
title: "backup_app_permissions"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/backup_app_permissions.html"
last_updated: "8/22/2024"
product_version: "8.3.0.2201"
---


In this article

The following table lists permissions for Microsoft Entra applications that you [add as backup applications](adding_backup_applications.md).

|  |
| --- |
| Note |
| Using multiple applications may impact the performance of your production SharePoint environment. This functionality will be deprecated in future versions of Veeam Backup for Microsoft 365. |

All listed permissions are of the Application type and required for data backup.

| API | Permission name | Exchange Online | SharePoint Online and OneDrive for Business | Microsoft Teams | Description |
| --- | --- | --- | --- | --- | --- |
| Microsoft Graph | Sites.Read.All |  | ✔ |  | Getting download URLs for files and their versions.  Note: In the Microsoft Entra China region, the Sites.ReadWrite.All permission is used instead. |
| Office 365 SharePoint Online | Sites.FullControl.All |  | ✔ |  | Reading SharePoint sites and OneDrive accounts content. |
| User.Read.All |  | ✔ |  | Reading OneDrive accounts (getting site IDs). |

Page updated 8/22/2024

Page content applies to build 8.3.0.2201
