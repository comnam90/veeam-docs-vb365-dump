---
title: "Veeam Backup for Microsoft 365 Certificates"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_ssl_certificates_overview.html"
last_updated: "3/13/2026"
product_version: "8.4.0.1457"
---

# Veeam Backup for Microsoft 365 Certificates


Veeam Backup for Microsoft 365 uses the following certificates:

Veeam Backup for Microsoft 365 Certificates

| Certificate | Description |
| Veeam Backup for Microsoft 365 server certificate | Used to establish a secure connection and data exchange with a Windows-based backup proxy server deployed in a workgroup.  You can manage the certificate in the [security settings](vbo_security_settings.md).  Note: To connect to a Linux-based backup proxy server, Veeam Backup for Microsoft 365 uses either user credentials or, if the Identity/Pubkey authentication method is used — a public key and private key. For more information, see [Specify SSH Connection Settings](add_linux_proxy_ssh.md). |
| REST API certificate | Used to establish a secure connection and data exchange between Veeam Backup for Microsoft 365 REST API Service and the Veeam Backup for Microsoft 365 server. Restore Portal also uses this certificate to communicate with the Veeam Backup for Microsoft 365 server and perform restore operations through REST API.  You can install the certificate in the [REST API settings](vbo_rest_api_settings.md). |
| Microsoft Entra application certificate | Used to establish a secure connection and data exchange between Veeam Backup for Microsoft 365 and a Microsoft Entra application when adding Microsoft 365 organizations and configuring backup applications. For more information, see [Adding Microsoft 365 Organizations](vbo_add_office365_org.md) and [Adding Applications](adding_backup_applications.md).  You can install the certificate in the [organization settings](vbo_editing_org.md) and [Backup Applications Manager](removing_backup_applications.md).  Note: Starting from Veeam Backup for Microsoft 365 version 8.4, adding existing applications to the backup configuration or creating new applications in your Microsoft Entra ID is not supported. |
| Tenant authentication certificate | Used to authenticate tenants to Veeam Backup for Microsoft 365 with Microsoft organization credentials.  You can install the certificate in the [authentication settings](vbo_authentication_settings.md). |
| Restore operator authentication certificate | Used to authenticate restore operators to Veeam Backup for Microsoft 365 with Microsoft 365 credentials and encrypt network traffic between Veeam Backup for Microsoft 365 Service and Veeam Backup for Microsoft 365 REST API Service.  You can install the certificate in the [authentication settings](vbo_authentication_settings.md). |
| Restore Portal certificate | Used to establish a secure connection and data exchange between the Veeam Backup for Microsoft 365 server, Microsoft 365 organization, Microsoft Entra application, Veeam Backup for Microsoft 365 REST API Service and Restore Portal.  You can install the certificate in the [Restore Portal settings](vbo_restore_portal_settings.md). |


