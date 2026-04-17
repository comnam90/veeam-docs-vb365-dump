---
title: "Backup Application Permissions"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/backup_app_permissions.html"
last_updated: "3/13/2026"
product_version: "8.4.0.1457"
---

# Backup Application Permissions


The following table lists permissions for Microsoft Entra applications that you [added as backup applications](adding_backup_applications.md).

|  |
| --- |
| Note |
| Using multiple applications may impact the performance of your production SharePoint environment. Starting from Veeam Backup for Microsoft 365 version 8.4, this functionality became deprecated. |

All listed permissions are of the Application type and required for data backup.

Backup Application Permissions

| API | Permission name | Exchange Online | SharePoint Online and OneDrive for Business | Microsoft Teams | Description |
| Microsoft Graph | Sites.Read.All |  | ✔ |  | Getting download URLs for files and their versions.  Note: In the Microsoft Entra China region, the Sites.ReadWrite.All permission is used instead. |
| Office 365 SharePoint Online | Sites.FullControl.All |  | ✔ |  | Reading SharePoint sites and OneDrive accounts content. |
| User.Read.All |  | ✔ |  | Reading OneDrive accounts (getting site IDs). |


