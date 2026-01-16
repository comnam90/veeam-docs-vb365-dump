---
title: "vbo_required_permissions"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_required_permissions.html"
last_updated: "5/6/2025"
product_version: "8.3.0.2201"
---


In this article

Microsoft Organizations

Veeam Backup for Microsoft 365 uses Veeam Backup account and Microsoft Entra application to establish and maintain connection between Veeam Backup for Microsoft 365 and Microsoft 365 organizations or on-premises Microsoft organizations and perform backup and restore of the organization data.

What the product requires depends on a Microsoft organization type and an authentication method used to add a Microsoft 365 organization.

The following options are available:

* For on-premises Microsoft organizations, Veeam Backup for Microsoft 365 uses only Veeam Backup account.
* For Microsoft 365 organizations, it depends on an authentication method that you use when adding a particular Microsoft 365 organization.

In all supported regions, you can add Microsoft 365 organizations using [modern app-only authentication](adding_o365_organizations_sd.md) method.

|  |
| --- |
| Note |
| Adding Microsoft 365 organizations using basic authentication method is only available in Microsoft Entra China region. In version 8, this functionality is not supported in the Veeam Backup for Microsoft 365 user interface, but still available in REST API and PowerShell. To add Microsoft 365 organization using basic authentication method in Microsoft Entra China region, run the [Add-VBOOrganization](https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboorganization.html?ver=80) cmdlet or use the POST /Organizations method. This functionality will be deprecated in future versions of Veeam Backup for Microsoft 365. |

Consider the following:

* For Microsoft 365 organizations with modern app-only authentication, Veeam Backup for Microsoft 365 uses a Microsoft Entra application and a user account that this Microsoft Entra application uses to log in to Microsoft 365.

* For Microsoft 365 organizations with basic authentication, Veeam Backup for Microsoft 365 uses only Veeam Backup account.

* Since [Microsoft deprecated basic authentication and legacy authentication protocols](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-september/ba-p/3609437), Veeam Backup for Microsoft 365 version 8 does not support adding new Microsoft 365 organizations using modern authentication method with legacy protocols allowed.

However, you can continue to use Veeam Backup for Microsoft 365 to back up and restore data of Microsoft 365 organizations that were added to previous installations of the product using this legacy authentication method. For Microsoft 365 organizations that were previously added using modern authentication method with legacy protocols allowed, Veeam Backup for Microsoft 365 uses both Veeam Backup account and Microsoft Entra application. The product requires MFA-enabled Microsoft 365 user account as Veeam Backup account.

Depending on authentication methods used for Microsoft organizations, you must grant permissions to Veeam Backup account or Microsoft Entra application, or both entities. For more information, see [Veeam Backup Account Permissions](permissions_veeam_backup_account.md) and [Microsoft Entra Application Permissions](azure_ad_applications.md).

Restore Portal

If you allow users to perform [self-service restore](ssp_restore.md) using Restore Portal, you must grant permissions to a Microsoft Entra application to ensure users authentication to the portal with their Microsoft 365 user account credentials. For more information, see [Permissions for Authentication to Restore Portal](ssp_ad_application_permissions.md).

Azure Archiver Appliance

If you want to use the [Azure archiver appliance](new_azure_backup_proxy.md) when Veeam Backup for Microsoft 365 copies backed-up data between different instances of Azure Blob Storage or to Azure Blob Storage Archive, you must assign the required roles to a user account that you use to create a Microsoft Entra application for the [Microsoft Azure service account](azure_service_account.md). For more information, see [Permissions for Azure Archiver Appliance](azure_archiver_appliance_permissions.md).

Amazon S3 Storage

If you want to store Microsoft 365 and on-premises Microsoft organization backups and backup copies in Amazon S3 object storage repository, you must grant permissions for each Amazon S3 object storage repository and allow a user account access to Amazon buckets and folders. For more information, see [Amazon S3 Storage Permissions](amazon_s3_permissions.md).

Azure Blob Storage and Azure Blob Storage Archive

If you want to store Microsoft 365 and on-premises Microsoft organization backups and backup copies in Azure Blob Storage and Azure Blob Storage Archive, you must grant permissions to a user account that you use to access this object storage repository. For more information, see [Azure Blob Storage Permissions](azure_archive_permissions.md).

Linux-based Backup Proxy Server

You can add Linux-based backup proxy servers to the Veeam Backup for Microsoft 365 backup infrastructure. A service account must be granted permissions to run Veeam Backup for Microsoft 365 Proxy Service on a machine with Linux operating systems installed. For more information, see [Permissions for Service Account on Linux](permissions_linux.md).

Windows-based Backup Proxy Server

You can add Windows-based backup proxy servers to the Veeam Backup for Microsoft 365 backup infrastructure. A service account must be granted permissions to run Veeam Backup for Microsoft 365 Proxy Service on a machine with Windows operating systems installed. For more information, see [Permissions for Service Account on Windows](permissions_windows.md).

In This Section

* [Veeam Backup Account Permissions](permissions_veeam_backup_account.md)
* [Microsoft Entra Application Permissions](azure_ad_applications.md)
* [Amazon S3 Storage Permissions](amazon_s3_permissions.md)
* [Azure Blob Storage Permissions](azure_archive_permissions.md)
* [Permissions for Service Account on Linux](permissions_linux.md)
* [Permissions for Service Account on Windows](permissions_windows.md)
* [Permissions Changelog](permissions_changelog.md)

Page updated 5/6/2025

Page content applies to build 8.3.0.2201
