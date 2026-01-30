---
title: "For Service Providers"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_baas_sp.html"
last_updated: "11/19/2025"
product_version: "8.3.0.2201"
---

# For Service Providers


To configure Backup as a Service with Veeam Backup for Microsoft 365 for service providers, do the following:

1. Install Veeam Backup for Microsoft 365 on a server with Veeam Backup & Replication with the enabled Cloud Connect feature.

For more information, see the [Deployment](vbo_deployment.md) section of this guide and the [Installing Veeam Backup & Replication](https://helpcenter.veeam.com/docs/vbr/userguide/install_vbr.html?ver=13) section of the Veeam Backup & Replication User Guide.

1. Install Veeam Backup for Microsoft 365 and Veeam Backup & Replication licenses.

For more information, see the [Licensing and License Types](vbo_licensing.md) of this guide and the [Veeam Cloud Connect License](https://helpcenter.veeam.com/docs/vbr/cloud/cloud_connect_sp_license.html) section of the Veeam Cloud Connect Guide.

1. Configure a TLS certificate. For more information, see the [Managing TLS Certificates](https://helpcenter.veeam.com/docs/vbr/cloud/cloud_connect_manage_ssl.html) section of the Veeam Cloud Connect Guide.

Without a certificate, you will not be able to add a Cloud Gateway component.

1. Configure a cloud gateway. For more information, see the [Adding Cloud Gateways](https://helpcenter.veeam.com/docs/vbr/cloud/cloud_connect_gateways.html) section of the Veeam Cloud Connect Guide.
2. Add new tenants. For more information, see the [Configuring Standalone Tenant Account](https://helpcenter.veeam.com/docs/vbr/cloud/cloud_connect_user.html) section of the Veeam Cloud Connect Guide.
3. Configure your Veeam Backup for Microsoft 365 environment. For more information, see [Configuring Veeam Backup for Microsoft 365](vbo_vbo_conf_sp.md).

To allow end users from tenant organizations to browse and restore their backups without using Veeam Explorers, a service provider can use the following:

* Restore Portal. For more information, see [Data Restore Using Restore Portal](ssp_restore.md).

* Web portal created using Veeam Backup for Microsoft 365 REST API. For more information, see [REST API Reference](https://helpcenter.veeam.com/references/vbo365/8/rest/).

|  |
| --- |
| Note |
| Consider the following:   * Make sure that a machine with Veeam Backup for Microsoft 365 meets the Veeam Service Provider Console system requirements. For more information. see the [System Requirements](https://helpcenter.veeam.com/docs/vac/deployment/system_requirements.html) section of the Veeam Service Provider Console Deployment Guide. * Make sure to install Veeam Explorer for Microsoft Exchange, Veeam Explorer for Microsoft SharePoint, Veeam Explorer for Microsoft OneDrive for Business and Veeam Explorer for Microsoft Teams that come as part of the Veeam Backup for Microsoft 365 8 installation package. For more information, see [Installing Veeam Backup for Microsoft 365](vbo_installing_vbo.md). * Make sure to install Veeam Backup for Microsoft 365 on a server with Veeam Backup & Replication 12 or later. |


