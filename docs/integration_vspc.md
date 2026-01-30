---
title: "Integration with Veeam Products"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/integration_vspc.html"
last_updated: "9/9/2025"
product_version: "8.3.0.2201"
---

# Integration with Veeam Products


Integration with Veeam Service Provider Console

Veeam Backup for Microsoft 365 supports integration with Veeam Service Provider Console that monitors licenses consumed by Veeam Backup for Microsoft 365 servers and the state of the product services. Integration is available starting from Veeam Service Provider Console version 6.0. For more information, see the [Integration with Veeam Backup for Microsoft 365](https://helpcenter.veeam.com/docs/vac/provider_admin/integration_vbo.html) section of the Veeam Service Provider Console Guide for Service Providers.

Integration with Veeam ONE

Starting from version 12.0, Veeam ONE Client offers advanced functionality for monitoring Veeam Backup for Microsoft 365 infrastructure and data protection operations in the managed virtual environment. For more information, see the [Veeam Backup for Microsoft 365 Monitoring](https://helpcenter.veeam.com/docs/one/userguide/vbo_monitoring.html) section of the Veeam ONE Monitoring Guide.

|  |
| --- |
| Note |
| Consider the following:   * Veeam ONE monitoring is available if Veeam Backup for Microsoft 365 has Subscription license with the M365Suite license package. * Veeam ONE monitoring is not supported for on-premises and hybrid Microsoft organizations. * For Veeam Backup for Microsoft 365 with Rental license, Veeam ONE monitoring is available if Veeam ONE also has Rental license. * To support integration with Veeam ONE after upgrading Veeam Backup for Microsoft 365 to version 8, you can either wait 7 days for the automatic license package update or update the current license manually, or install a new license. For more information, see [Installing and Updating License](vbo_installing_license.md#monitoring). |

For more information on the compatibility of Veeam Backup for Microsoft 365 licenses with Veeam ONE licenses, see the [Compatibility with Veeam Backup for Microsoft 365 Licenses](https://helpcenter.veeam.com/docs/one/userguide/license_types.html?ver=13#compatibility-with-veeam-backup-for-microsoft-365-licenses) section of the Veeam ONE Deployment Guide and [this Veeam KB article](https://www.veeam.com/kb4422).

By default, Veeam ONE collects data from Veeam Backup for Microsoft 365 REST API over HTTPS through the port 4443.

Organization Cache Database

To ensure integration, Veeam Service Provider Console and Veeam ONE get information from an organization cache database created by Veeam Backup for Microsoft 365 as part of the product configuration database. The configuration database is created on a new or already installed PostgreSQL instance. Data is saved to the file with the VeeamBackup365 name located by default in the C:\Program Files\PostgreSQL\15\data folder on a machine with the PostgreSQL instance.

Veeam Backup for Microsoft 365 uses the organization cache database to store information about all restore points created for Microsoft 365 organizations and to index all objects in Microsoft 365 organizations with modern app-only authentication. For more information about synchronization of Microsoft organization objects with the organization cache database, see the [Synchronization of Organization Objects](https://helpcenter.veeam.com/references/vbo365/8/rest/tag/OrganizationSync) section of REST API Reference.

|  |
| --- |
| Note |
| Veeam Backup for Microsoft 365 does not save information about restore points created for retrieval jobs in the organization cache database. |


