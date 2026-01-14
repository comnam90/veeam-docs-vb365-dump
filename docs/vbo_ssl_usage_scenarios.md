---
title: "vbo_ssl_usage_scenarios"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_ssl_usage_scenarios.html"
last_updated: "9/22/2025"
product_version: "8.3.0.2201"
---


In this article

The following table lists usage scenarios when Veeam Backup for Microsoft 365 requires to install an SSL certificate.

|  |
| --- |
| Note |
| An SSL certificate that you want to use must have a private key. |

| Usage Scenario | Description | Reference |
| --- | --- | --- |
| Managing Microsoft 365 Organization | Required to establish communication and data exchange between Veeam Backup for Microsoft 365 and Microsoft Entra application when adding Microsoft 365 organizations. | For more information, see [Adding Microsoft 365 Organizations](vbo_add_office365_org.md). |
| Required to establish communication and data exchange between Veeam Backup for Microsoft 365 and Microsoft Entra application when configuring backup applications. | For more information, see [Backup Applications](backup_applications.md). |
| Communicating with Backup Proxy Server | Required to establish communication and data exchange between the Veeam Backup for Microsoft 365 server and a Windows-based backup proxy server deployed in a workgroup.  Note: To connect to a Linux-based backup proxy server, Veeam Backup for Microsoft 365 uses either user credentials or, if the Identity/Pubkey authentication method is used — a public key and private key. For more information, see [Specify SSH Connection Settings](add_linux_proxy_ssh.md). | For more information, see [Security Settings](vbo_security_settings.md). |
| Communicating with REST API on Veeam Backup for Microsoft 365 server | Required to establish communication and data exchange between the following:   * Veeam Backup for Microsoft 365 REST API Service and the Veeam Backup for Microsoft 365 server * Restore Portal and Veeam Backup for Microsoft 365 | For more information, see [REST API Settings](vbo_rest_api_settings.md). |
| Communicating with REST API on Separate Machine | Required to establish communication and data exchange between the following:   * Veeam Backup for Microsoft 365 REST API Service and the Veeam Backup for Microsoft 365 server * Restore Portal and Veeam Backup for Microsoft 365 | For more information, see [Configuring REST API and Restore Portal on Separate Machine](vbo_configuring_rest_separate.md#rest). |
| Communicating with Restore Portal | Required to establish communication and data exchange between the Veeam Backup for Microsoft 365 server, Microsoft 365 organization, Microsoft Entra application, Veeam Backup for Microsoft 365 REST API Service and Restore Portal. | For more information, see [Restore Portal Settings](vbo_restore_portal_settings.md), [Configuring REST API and Restore Portal on Separate Machine](vbo_configuring_rest_separate.md#ssp), [How Restore Portal Works](ssp_how_it_works.md). |
| Authenticating Restore Operators to Veeam Backup for Microsoft 365 server | Required to authenticate restore operators to Veeam Backup for Microsoft 365 with Microsoft 365 credentials and encrypt network traffic between Veeam Backup for Microsoft 365 Service and Veeam Backup for Microsoft 365 REST API Service. | For more information, see [Authentication Settings](vbo_authentication_settings.md#restore_operator). |
| Authenticating Tenants to Veeam Backup for Microsoft 365 in Service Provider Infrastructure | Required to authenticate tenants to Veeam Backup for Microsoft 365 with Microsoft organization credentials. | For more information, see [Authentication Settings](vbo_authentication_settings.md#tenants) and [Backup as Service with Veeam Backup for Microsoft 365](vbo_mail_baas.md). |

Page updated 9/22/2025

Page content applies to build 8.3.0.2201
