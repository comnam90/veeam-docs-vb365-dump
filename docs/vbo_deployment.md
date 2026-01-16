---
title: "vbo_deployment"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_deployment.html"
last_updated: "9/16/2025"
product_version: "8.3.0.2201"
---


In this article

To start working with Veeam Backup for Microsoft 365, you must deploy the solution to your environment. For more information about Veeam Backup for Microsoft 365 architecture, see [Veeam Backup for Microsoft 365 Architecture](architecture.md).

Consider the following:

* If you have been participating in the public beta testing of Veeam Backup for Microsoft 365, make sure to uninstall the pre-release (BETA) versions of Veeam Backup for Microsoft 365 and Veeam Explorers.
* To use the solution in hybrid Exchange deployment or on-premises organizations with SPN and Kerberos authentication, make sure to install Veeam Backup for Microsoft 365 on a server that is located within the domain with the source Microsoft Exchange server.
* The solution can be deployed to virtual or physical machines or directly to cloud platforms such as Microsoft Azure or Amazon Web Services (AWS).
* Veeam Backup for Microsoft 365 REST API component can be deployed either on the Veeam Backup for Microsoft 365 server or on a separate machine. Deployment of the Veeam Backup for Microsoft 365 REST API component on a separate machine decreases the load on the backup infrastructure when exploring and restoring data from backups using Restore Portal. For more information, see [Installing REST API](vbo_installing_rest.md), [Configuring REST API and Restore Portal on Separate Machine](vbo_configuring_rest_separate.md) and [Data Restore Using Restore Portal](ssp_restore.md).
* You can deploy a PostgreSQL instance and the NATS server on the Veeam Backup for Microsoft 365 server, or you can use the already installed instances.

In This Section

* [Downloading Installation Package](download_package.md)
* [Installing Veeam Backup for Microsoft 365](vbo_installing_vbo.md)
* [Installing Veeam Backup for Microsoft 365 Console](vbo_installing_console.md)
* [Installing PowerShell Toolkit](vbo_installing_ps.md)
* [Installing REST API](vbo_installing_rest.md)
* [Installing Veeam Explorers](vbo_installing_explorers_for_tenants.md)
* [Installing in Unattended Mode](vbo_installing_in_unattended.md)
* [Deploying to Microsoft Azure and AWS](vbo_installing_azure_aws.md)
* [Updating Veeam Backup for Microsoft 365](vbo_updating.md)
* [Installing and Updating License](vbo_installing_license.md)
* [Uninstalling License](vbo_uninstall_license.md)
* [Upgrading Veeam Backup for Microsoft 365](vbo_upgrading.md)
* [Upgrading REST API on Separate Machine](restapi_upgrading.md)
* [Uninstalling Veeam Backup for Microsoft 365](vbo_uninstall.md)

Page updated 9/16/2025

Page content applies to build 8.3.0.2201
