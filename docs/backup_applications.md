---
title: "Backup Applications"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/backup_applications.html"
last_updated: "3/13/2026"
product_version: "8.4.0.1457"
---

# Backup Applications


|  |
| --- |
| Note |
| Starting from Veeam Backup for Microsoft 365 version 8.4, adding existing applications to the backup configuration or creating new applications in your Microsoft Entra ID is not supported. Those auxiliary backup applications that have already been added to Veeam Backup for Microsoft 365, are kept running. You can remove them if needed. |

You can use [Microsoft Entra applications](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-how-applications-are-added) for Microsoft 365 organizations added using modern app-only authentication to minimize throttling when backing up Microsoft SharePoint Online and Microsoft OneDrive for Business data.

Consider the following:

* Using multiple applications may impact the performance of your production SharePoint environment. For more information, see [Impact of Multiple Backup Applications on Performance](impact_on_performance.md).

* A Microsoft Entra application that you used to add your Microsoft 365 organization to Veeam Backup for Microsoft 365 is included in the pool of auxiliary backup applications by default.
* For security purposes, data exchange between Microsoft Entra applications and Veeam Backup for Microsoft 365 is maintained using TLS certificates only; you cannot use an [application secret](https://docs.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal#certificates-and-secrets).

* For Microsoft 365 organizations added using either basic authentication or modern authentication method with legacy protocols allowed, you use backup accounts instead. For more information, see [Backup Accounts](backup_accounts.md).

In This Section

* [Impact of Multiple Backup Applications on Performance](impact_on_performance.md)
* [Backup Application Permissions](backup_app_permissions.md)
* [Adding Applications](adding_backup_applications.md)
* [Creating Applications](creating_backup_applications.md)
* [Updating Certificates and Removing Applications](removing_backup_applications.md)


