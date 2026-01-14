---
title: "vbo_baas_tenant"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_baas_tenant.html"
last_updated: "11/19/2025"
product_version: "8.3.0.2201"
---


In this article

To configure Backup as a Service with Veeam Backup for Microsoft 365 for tenants, do the following:

1. Add a service provider in Veeam Backup & Replication. For more information, see the [Connecting to Service Providers](https://helpcenter.veeam.com/docs/vbr/cloud/cloud_connect_sp.html) section of the Veeam Cloud Connect Guide.
2. Add backups to the Veeam Explorer scope. For more information, see [Exploring Backups in Veeam Explorers](vbo_vex_adding_store.md).

|  |
| --- |
| Note |
| Consider the following:   * Make sure to install Veeam Explorer for Microsoft Exchange, Veeam Explorer for Microsoft SharePoint, Veeam Explorer for Microsoft OneDrive for Business and Veeam Explorer for Microsoft Teams that come as part of the Veeam Backup for Microsoft 365 8 installation package. For more information, see [Installing Veeam Explorers](vbo_installing_explorers_for_tenants.md). * By default, tenants cannot restore anything without the service provider assistance. To be able to perform self-restore procedures, a service provider must configure authentication settings for tenants. For more information, see [Authentication Settings](vbo_authentication_settings.md#tenants).  * Tenants must provide service providers with their Microsoft organization credentials. Tenants can use the same credentials when adding a Veeam Backup for Microsoft 365 service provider server to the Veeam Explorers scope. For more information, see [Exploring Backups in Veeam Explorers](vbo_vex_adding_store.md).  * If the service provider allows end users from a tenant organization to perform [self-service restore](ssp_operation_scenarios.md) using Restore Portal, ensure that data restore using Restore Portal is configured on the tenant side. For more information, see [On Tenant Side](ssp_configuration.md#tenantside). |

Page updated 11/19/2025

Page content applies to build 8.3.0.2201
