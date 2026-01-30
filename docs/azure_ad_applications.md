---
title: "Microsoft Entra Application Permissions"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/azure_ad_applications.html"
last_updated: "8/22/2024"
product_version: "8.3.0.2201"
---

# Microsoft Entra Application Permissions


Veeam Backup for Microsoft 365 requires that you grant permissions to Microsoft Entra applications within the following usage scenarios:

* [Back up](vbo_data_backup.md) and [restore](vbo_data_restore.md) data of your Microsoft 365 organizations.

Permissions of the Microsoft Entra application depend on the authentication method used for a Microsoft 365 organization. For more information about permissions for Microsoft organizations with modern app-only authentication, see [Permissions for Modern App-Only Authentication](ad_app_permissions_sd.md).

|  |
| --- |
| Note |
| Since [Microsoft deprecated basic authentication and legacy authentication protocols](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-september/ba-p/3609437), you cannot add new Microsoft 365 organizations to Veeam Backup for Microsoft 365 using modern authentication method with legacy protocols allowed. However, you can continue to use Veeam Backup for Microsoft 365 to back up and restore data of Microsoft 365 organizations that were added to previous installations of the product using this authentication method. For more information about permissions that must be granted to Microsoft Entra applications, see [Permissions for Modern Authentication and Legacy Protocols](ad_app_permissions_legacy.md). |

* [Self-service restore](ssp_restore.md) using Restore Portal.

If you allow users to perform self-service restore using Restore Portal, they will authenticate to the portal with their Microsoft 365 user account credentials. To ensure such authentication, a Microsoft Entra application must be configured. Veeam Backup for Microsoft 365 automatically grants the required permissions to this Microsoft Entra application or you can grant permissions manually. For more information, see the following sections:

* [Permissions for Authentication to Restore Portal](ssp_ad_application_permissions.md)
* [Creating or Configuring Microsoft Entra Application](ssp_create_new_app_wizard.md)

* [Backup copy](vbo_backup_copy.md) to Microsoft Azure Blob Storage.

You can optionally use the [Azure archiver appliance](new_azure_backup_proxy.md) when Veeam Backup for Microsoft 365 copies backed-up data between different instances of Azure Blob Storage or to Azure Blob Storage Archive. To enable usage of the Azure archiver appliance, the Microsoft Azure service account is required. You must assign the required roles to a user account that you use to create a Microsoft Entra application for the Microsoft Azure service account. Veeam Backup for Microsoft 365 automatically grants the required permissions to this Microsoft Entra application or you can grant permissions manually. For more information, see the following sections:

* [Permissions for Azure Archiver Appliance](azure_archiver_appliance_permissions.md)
* [Adding Microsoft Azure Service Account](azure_service_account.md)

For more information about Microsoft Graph permissions, see [this Microsoft article](https://docs.microsoft.com/en-us/graph/permissions-reference).


