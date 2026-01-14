---
title: "download_package"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/download_package.html"
last_updated: "11/11/2025"
product_version: "8.3.0.2201"
---


In this article

You can download the latest version of the Veeam.Backup365.iso file — the Veeam Backup for Microsoft 365 installation image — from the official [Veeam website](https://www.veeam.com/products/saas/backup-microsoft-office-365-download.html).

The Veeam.Backup365.iso file includes the following folders and files:

* Backup. This folder includes the Veeam.Backup365.msi file.

* Explorers. This folder includes MSI files that install Veeam Explorers:

* VeeamExplorerForExchange.msi — installs Veeam Explorer for Microsoft Exchange.

For more information, see [Veeam Explorer for Microsoft Exchange](https://helpcenter.veeam.com/docs/vbo365/explorers/vex_user_guide.html?ver=80).

* VeeamExplorerForSharePoint.msi — installs Veeam Explorer for Microsoft SharePoint and Veeam Explorer for Microsoft OneDrive for Business.

For more information, see [Veeam Explorer for Microsoft SharePoint](https://helpcenter.veeam.com/docs/vbo365/explorers/vesp_user_guide.html?ver=80) and [Veeam Explorer for Microsoft OneDrive for Business](https://helpcenter.veeam.com/docs/vbo365/explorers/veod_user_guide.html?ver=80).

* VeeamExplorerForTeams.msi — installs Veeam Explorer for Microsoft Teams.

For more information, see [Veeam Explorer for Microsoft Teams](https://helpcenter.veeam.com/docs/vbo365/explorers/vet_user_guide.html?ver=80).

* [Optional] Patches. If exists, this folder includes MSP files that Windows uses to install cumulative patches along with the Veeam Backup for Microsoft 365 and Veeam Explorers installation.

* Redistr. This folder includes installation files to deploy the following software components:

* Microsoft .NET Framework 4.7.2
* Microsoft ASP.NET Core Runtime 8.0.xx
* Microsoft .NET Desktop Runtime 8.0.xx
* Microsoft .NET Runtime 8.0.xx
* NATS server 2.10.28
* PostgreSQL 15.14
* Windows PowerShell 7.4.xx
* Microsoft Visual C++

* Setup. This folder includes Veeam License Agreement and licensing policy as well as license agreements of the 3rd party components that Veeam incorporates and license agreements of the required software, Veeam.Archiver.Autorun.exe, and other files required for the installation and operation of Veeam Backup for Microsoft 365.

* autorun.inf — includes the setup information.
* Veeam.Setup.exe — launches the Veeam Backup for Microsoft 365 installation wizard.

Related Topics

* [Installing Veeam Backup for Microsoft 365](vbo_installing_vbo.md)
* [Installing Veeam Backup for Microsoft 365 Console](vbo_installing_console.md)
* [Installing PowerShell Toolkit](vbo_installing_ps.md)
* [Installing REST API](vbo_installing_rest.md)
* [Configuring REST API and Restore Portal on Separate Machine](vbo_configuring_rest_separate.md)
* [Installing Veeam Explorers](vbo_installing_explorers_for_tenants.md)
* [Installing in Unattended Mode](vbo_installing_in_unattended.md)

Page updated 11/11/2025

Page content applies to build 8.3.0.2201
