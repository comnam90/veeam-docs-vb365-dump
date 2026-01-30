---
title: "Backup Accounts"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/backup_accounts.html"
last_updated: "8/23/2024"
product_version: "8.3.0.2201"
---

# Backup Accounts


For Microsoft 365 organizations added using either basic authentication or modern authentication method with legacy protocols allowed, you can configure auxiliary backup accounts to minimize throttling when backing up Microsoft SharePoint and OneDrive for Business data.

In Veeam Backup for Microsoft 365 version 8, you can add a Microsoft 365 organization using basic authentication only in Microsoft Entra China region. This functionality is only available through REST API and PowerShell. Adding Microsoft organizations using modern authentication method with legacy protocols allowed is not supported. However, after upgrading Veeam Backup for Microsoft 365 to version 8 from the previous versions of the product, you may have in the Veeam Backup for Microsoft 365 console such organizations that use legacy authentication methods. Veeam Backup for Microsoft 365 continues to support auxiliary backup accounts for these organizations.

To configure backup accounts, you use Microsoft 365 user accounts. You do not need to grant them any permissions or assign roles to them. Veeam Backup for Microsoft 365 automatically assigns the required roles to configured backup accounts.

|  |
| --- |
| Note |
| For Microsoft 365 organizations added using modern app-only authentication, you use backup applications instead. For more information, see [Backup Applications](backup_applications.md). |

In This Section

* [Adding Accounts](adding_backup_accounts.md)
* [Changing Password and Removing Accounts](editing_and_removing_accounts.md)


