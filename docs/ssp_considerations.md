---
title: "ssp_considerations"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/ssp_considerations.html"
last_updated: "3/24/2025"
product_version: "8.3.0.2201"
---


In this article

This section lists considerations and known limitations of Restore Portal.

* Restore Portal is supported only for organizations added to Veeam Backup for Microsoft 365 using the modern app-only authentication method. Microsoft Entra application that you have used to add your Microsoft 365 organization must have [permissions](ad_app_permissions_sd.md#appcert) for data restore using an application certificate.

* Backups created for on-premises Microsoft organizations cannot be restored using Restore Portal. For hybrid organizations, Restore Portal allows you to restore only data from backups created for Microsoft 365 organizations.
* Group mailboxes data is not supported for explore and restore using Restore Portal.
* Items of different types that you added to the restore list (for example, mailbox items, OneDrive and SharePoint files) will not be restored simultaneously. You must configure and run different restore operations for Exchange, SharePoint, OneDrive and Teams items.
* Backup copies and backups that were retrieved from backup copies cannot be explored and restored using Restore Portal.

* If you want to use Restore Portal to restore backed-up data of Microsoft 365 organizations that belong to [different regions](vbo_add_o365_2_sd.md), you must use a separate installation of the Veeam Backup for Microsoft 365 REST API component and a separate Microsoft Entra application in each Microsoft Entra region.

Page updated 3/24/2025

Page content applies to build 8.3.0.2201
