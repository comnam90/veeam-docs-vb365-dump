---
title: "vbo_installing_vbo"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_installing_vbo.html"
last_updated: "9/16/2025"
product_version: "8.3.0.2201"
---


In this article

This installation scenario allows you to install Veeam Backup for Microsoft 365 along with Veeam Explorers on a physical or virtual Windows-based machine. After completing the installation process, this machine will perform the role of the Veeam Backup for Microsoft 365 server.

The wizard deploys the following components of Veeam Backup for Microsoft 365:

* Services:

* Veeam Backup for Microsoft 365 Service

Coordinates all operations performed by the product, adds and manages other backup infrastructure components as well as controls global settings for the backup infrastructure.

* Veeam Backup for Microsoft 365 Proxy Service

Manages backup proxy servers and backup repositories.

* Veeam Backup for Microsoft 365 REST API Service

Processes REST API commands. This service is disabled by default and can be enabled. For more information, see [REST API Settings](vbo_rest_api_settings.md).

Restore Portal is deployed along with REST API on the same machine. Restore Portal is a web-based solution for self-service restore of backed-up data. Restore Portal uses REST API to communicate with the Veeam Backup for Microsoft 365 server. For more information, see [Data Restore Using Restore Portal](ssp_restore.md).

* Veeam Backup for Microsoft 365 Console

Provides an interface that allows users to interact with the Veeam Backup for Microsoft 365 server and backup infrastructure components.

* Veeam Backup for Microsoft 365 PowerShell toolkit

Includes sets of PowerShell cmdlets and allows you to run Veeam Backup for Microsoft 365 PowerShell sessions.

* Veeam Explorers

Set of instruments that comes as part of Veeam Backup for Microsoft 365 and allows you to restore or export your data from backups.

The wizard also deploys a PostgreSQL instance and the NATS server locally on a target machine, or you can use the already installed instances.

Before you install Veeam Backup for Microsoft 365, [check prerequisites](vbo_install_before_you_begin.md).

To install Veeam Backup for Microsoft 365 along with Veeam Explorers, do the following:

1. [Launch the installation wizard](vbo_install_launch.md).
2. [Select the component to install](vbo_install_select_vbo.md).
3. [Read and accept the license agreement](vbo_install_agreements.md).
4. [Provide a license file](vbo_install_license_file.md).
5. [Check the system configuration](vbo_install_configuration_check.md).
6. [Review the default installation settings](vbo_install_default_settings.md).
7. [Specify data location](vbo_install_data_location.md).
8. [Configure the PostgreSQL instance](vbo_install_configure_instance.md).
9. [Configure the NATS server](vbo_install_configure_nats.md).
10. [Begin the installation process](vbo_install_begin.md).

Related Topics

* [Adjusting PostgreSQL Instance Configuration](adjust_postgres_instance.md)
* [Enabling TLS Encryption on NATS Server](adjust_nats_instance.md)

Page updated 9/16/2025

Page content applies to build 8.3.0.2201
