---
title: "vbo_upgrading"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_upgrading.html"
last_updated: "11/11/2025"
product_version: "8.3.0.2201"
---


In this article

You can upgrade Veeam Backup for Microsoft 365 by installing a major version of the product.

Veeam Backup for Microsoft 365 supports upgrade to version 8.3 from the following versions of the product:

* 7.0 (builds 7.0.0.2911, 7.0.0.2914, 7.0.0.3007, 7.0.0.3604, 7.0.0.3968, 7.0.0.4385, 7.0.0.4388, 7.0.0.4551, 7.0.0.4901)
* 7a (builds 7.1.0.1301, 7.1.0.1401, 7.1.0.1501, 7.1.0.1502, 7.1.0.2031)
* 8 (builds 8.0.2.159, 8.0.2.200, 8.0.3.1044, 8.0.3.1073, 8.0.4.29, 8.0.5.20)
* 8.1 (builds 8.1.0.305, 8.1.0.331, 8.1.0.3503, 8.1.1.159, 8.1.2.180, 8.1.2.3301)
* 8.2 (builds 8.2.0.2008, 8.2.0.2202)

|  |
| --- |
| Note |
| Veeam Backup for Microsoft 365 does not upgrade the PostgreSQL instance and the NATS server. You have to upgrade these components manually. For more information on the supported versions, see [System Requirements](vbo_system_requirements.md#ManagementServer). |

To upgrade Veeam Backup for Microsoft 365 and Veeam Explorers, do the following:

1. [Launch the upgrade wizard](vbo_upgrade_launch.md).
2. [Read and accept the license agreement](vbo_upgrade_agreements.md).
3. [Provide a license file](vbo_upgrade_license_file.md).
4. [Check the system configuration](vbo_upgrade_configuration_check.md).
5. [Review the Microsoft Entra application permissions](vbo_upgrade_app_permissions_check.md).
6. [Review the default installation settings](vbo_upgrade_default_settings.md).
7. [Configure the PostgreSQL instance](vbo_upgrade_configure_instance.md).
8. [Configure the NATS server](vbo_upgrade_configure_nats.md).
9. [Begin the installation process](vbo_upgrade_begin.md).

Related Topics

* [What You Do After Upgrade](after_upgrade.md)
* [Installing Veeam Backup for Microsoft 365](vbo_installing_vbo.md)
* [Installing REST API](vbo_installing_rest.md)

Page updated 11/11/2025

Page content applies to build 8.3.0.2201
