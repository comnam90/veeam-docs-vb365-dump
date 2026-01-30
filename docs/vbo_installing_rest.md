---
title: "Installing REST API"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_installing_rest.html"
last_updated: "3/24/2025"
product_version: "8.3.0.2201"
---

# Installing REST API


This installation scenario allows you to install the Veeam Backup for Microsoft 365 REST API component on a separate physical or virtual Windows-based machine. After completing the installation process, this machine will perform the role of the Veeam Backup for Microsoft 365 REST API server.

Restore Portal is deployed along with REST API on the same machine. Restore Portal is a web-based solution for self-service restore of backed-up data. Restore Portal uses REST API to communicate with the Veeam Backup for Microsoft 365 server. For more information, see [Data Restore Using Restore Portal](ssp_restore.md).

Deployment of the Veeam Backup for Microsoft 365 REST API component on a separate machine decreases the load on the backup infrastructure when exploring and restoring data from backups using Restore Portal.

Consider the following:

* Before you begin to deploy the Veeam Backup for Microsoft 365 REST API server on a separate machine, check [system requirements](vbo_system_requirements.md#restapi).
* If you want to use Restore Portal to restore backed-up data of Microsoft 365 organizations that belong to [different regions](vbo_add_o365_2_sd.md), you must use a separate installation of the Veeam Backup for Microsoft 365 REST API component and a separate Microsoft Entra application in each Microsoft Entra region.

|  |
| --- |
| Note |
| After you installed the Veeam Backup for Microsoft 365 REST API component on a separate machine, you must configure the REST API and Restore Portal settings. It is required to establish communication and data exchange between Veeam Backup for Microsoft 365, Veeam Backup for Microsoft 365 REST API Service and Restore Portal. For more information, see [Configuring REST API and Restore Portal on Separate Machine](vbo_configuring_rest_separate.md). |

To install the Veeam Backup for Microsoft 365 REST API component on a separate machine, do the following:

1. [Launch the installation wizard](vbo_install_launch_rest.md).
2. [Select the component to install](vbo_install_select_rest.md).
3. [Read and accept the license agreement](vbo_install_agreements_rest.md).
4. [Check the system configuration](vbo_install_configuration_check_rest.md).
5. [Review the default installation settings](vbo_install_default_settings_rest.md).
6. [Specify data location](vbo_install_data_location_rest.md).
7. [Begin the installation process](vbo_install_begin_rest.md).


