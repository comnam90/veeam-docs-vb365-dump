---
title: "vbo_used_ports"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_used_ports.html"
last_updated: "3/24/2025"
product_version: "8.3.0.2201"
---


In this article

The following table describes network ports that must be opened to ensure proper communication of the Veeam Backup for Microsoft 365 server with other backup infrastructure components and protected services.

Depending on Microsoft 365 subscription location, Veeam Backup for Microsoft 365 uses the following endpoints:

* Worldwide endpoints

The endpoints for worldwide Microsoft 365 subscriptions. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide).

* Microsoft 365 operated by 21 Vianet endpoints

The endpoints for Microsoft 365 operated by 21 Vianet which is designed to meet the needs for Microsoft 365 in China. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges-21vianet?view=o365-worldwide).

|  |
| --- |
| Note |
| Data communication between Microsoft 365 organizations and Veeam Backup for Microsoft 365 is performed through an SSL connection. |

| From | To | Protocol | Port | Description |
| --- | --- | --- | --- | --- |
| Veeam Backup for Microsoft 365 server | Microsoft Exchange Online | TCP | 443 | Required to connect to Microsoft Exchange Online organizations.  The Worldwide endpoints are: outlook.office365.com and autodiscover-s.outlook.com.  The Microsoft 365 operated by 21 Vianet endpoints are: partner.outlook.cn and autodiscover-s.partner.outlook.cn. |
| Microsoft SharePoint Online | TCP | 443 | Required to connect to Microsoft SharePoint Online organizations.  The Worldwide endpoints are: <tenant>.sharepoint.com, <tenant>-my.sharepoint.com and <tenant>-admin.sharepoint.com.  The Microsoft 365 operated by 21 Vianet endpoints are: <tenant>-admin.sharepoint.cn, <mytenant>-my.sharepoint.cn and <mytenant>sharepoint.cn. |
| On-premises Microsoft SharePoint server | HTTP (HTTPS) | 5985 (5986 — used by default) | Required to connect to on-premises Microsoft SharePoint organizations through the WinRM port. |
| On-premises Microsoft Exchange server | TCP | 80 or 443 | Required to connect to on-premises Microsoft Exchange organizations. |
| Backup proxy server | TCP | 9193 (used by default) | Required to manage inbound/outbound traffic when interacting with the Veeam Backup for Microsoft 365 server.  Make sure to open this port on a backup proxy server. |
| TCP | 445 | This port is used to:   * Install and manage the Veeam.Archiver.Proxy service on a target proxy machine. * Perform RPC requests. |
| SSH | 22 | Required to connect to a Linux machine.  Make sure to open this port on a Linux-based backup proxy server. |
| Veeam auto-update server | TCP | 443 | Required to access the auto-update server and licensing server. For more information, see [Updating Veeam Backup for Microsoft 365](vbo_updating.md) and [Installing and Updating License](vbo_installing_license.md).  The endpoints are: https://vbo.butler.veeam.com and download2.veeam.com. |
| TCP | 80 | Required for certificate validation when Veeam Backup for Microsoft 365 connects to licensing server to check if the new license is available to update the product license automatically.  The endpoints are: \*.ss2.us and \*.amazontrust.com.  Consider that certificate verification endpoints (CRL URLs and OCSP servers) are subject to change. The actual list of addresses can be found in the certificate itself. |
| S3 Compatible object storage repository / IBM Cloud Object Storage / Wasabi Cloud Object Storage | TCP | 443 | Required to work with object storage repositories.  The endpoint for Azure Blob Storage is <account>.blob.core.windows.net.  The endpoints for Amazon S3 object storage repository are s3.amazonaws.com and <bucketName>.s3.<regionName>.amazonaws.com. |
| Amazon S3 object storage repository |
| Azure Blob Storage |
| Microsoft 365 | TCP | 443 | Required to connect to Microsoft 365.  The Worldwide endpoints are: graph.microsoft.com, graph.windows.net and login.microsoftonline.com.  The Microsoft 365 operated by 21 Vianet endpoints are: login.partner.microsoftonline.cn and microsoftgraph.chinacloudapi.cn. |
| SMTP server | TCP | 25 or 465 or 587 | Required to send email notifications using an SMTP server.  The Worldwide endpoint is smtp.office365.com.  The Microsoft 365 operated by 21 Vianet endpoint is smtp-legacy.partner.outlook.cn. |
| PostgreSQL instance | TCP | 5432 (used by default) | Required to manage inbound/outbound traffic when accessing the Veeam Backup for Microsoft 365 configuration database.  Make sure to open this port on a PostgreSQL instance. |
| NATS server | TCP | 4222 (used by default) | Required to manage inbound/outbound traffic for communication between backup proxy servers within a backup proxy pool and the Veeam Backup for Microsoft 365 server.  Make sure to open this port on the NATS server. |
| Veeam Backup for Microsoft 365 components | Veeam Backup for Microsoft 365 server | TCP | 9191 | Required to manage inbound/outbound traffic when interacting with the following components:   * REST API * PowerShell * Veeam.Archiver.Shell (UI) * [Optionally] A remote management server (if any)   Make sure to open port on the Veeam Backup for Microsoft 365 server. |
| Veeam Explorer for Microsoft Exchange | Veeam Backup for Microsoft 365 server | TCP | 9194 | Required to manage inbound/outbound traffic when interacting with Veeam Explorer for Microsoft Exchange.  Make sure to open this port on the Veeam Backup for Microsoft 365 server. |
| Microsoft Exchange Online | TCP | 443 | Required to restore Microsoft Exchange data. |
| SMTP server | TCP | 25 or 465 or 587 | Required to send email notifications using an SMTP server.  The Worldwide endpoint is smtp.office365.com.  The Microsoft 365 operated by 21 Vianet endpoint is smtp-legacy.partner.outlook.cn. |
| Veeam Explorer for Microsoft SharePoint (including Veeam Explorer for Microsoft OneDrive for Business) | Veeam Backup for Microsoft 365 server | TCP | 9194 | Required to manage inbound/outbound traffic when interacting with Veeam Explorer for Microsoft SharePoint.  Make sure to open this port on the Veeam Backup for Microsoft 365 server. |
| Microsoft SharePoint Online | TCP | 443 | Required to restore Microsoft SharePoint data. |
| SMTP server | TCP | 25 or 465 or 587 | Required to send email notifications using an SMTP server.  The Worldwide endpoint is smtp.office365.com.  The Microsoft 365 operated by 21 Vianet endpoint is smtp-legacy.partner.outlook.cn. |
| Veeam Explorer for Microsoft Teams | Veeam Backup for Microsoft 365 server | TCP | 9194 | Required to manage inbound/outbound traffic when interacting with Veeam Explorer for Microsoft Teams.  Make sure to open this port on the Veeam Backup for Microsoft 365 server. |
| Microsoft Teams Online | TCP | 443 | Required to restore Microsoft Teams data.  The endpoint is developer.microsoft.com. |
| SMTP server | TCP | 25 or 465 or 587 | Required to send email notifications using an SMTP server.  The Worldwide endpoint is smtp.office365.com.  The Microsoft 365 operated by 21 Vianet endpoint is smtp-legacy.partner.outlook.cn. |
| Backup proxy server1 | Veeam Backup for Microsoft 365 server | TCP | 9191 | Required to manage inbound/outbound traffic when interacting with backup proxy servers.  Make sure to open this port on the Veeam Backup for Microsoft 365 server.  You can also change this port. For more information, see [Editing Backup Proxy Server Settings](vbo_editing_proxy_server.md). |
| Backup proxy server | TCP | 9193 | Required to move an organization data between repositories.  Make sure to open this port on each backup proxy server. |
| Microsoft Exchange Online | TCP | 443 | Required to connect to Microsoft Exchange Online through EWS (Exchange Web Services).  The Worldwide endpoints are: outlook.office365.com and autodiscover-s.outlook.com.  The Microsoft 365 operated by 21 Vianet endpoints are: partner.outlook.cn and autodiscover-s.partner.outlook.cn. |
| Microsoft SharePoint Online | TCP | 443 | Required to connect to Microsoft SharePoint Online organizations.  The Worldwide endpoints are: <tenant>.sharepoint.com, <tenant>-my.sharepoint.com and <tenant>-admin.sharepoint.com.  The Microsoft 365 operated by 21 Vianet endpoints are: <tenant>-admin.sharepoint.cn, <mytenant>-my.sharepoint.cn and <mytenant>sharepoint.cn. |
| On-premises Microsoft SharePoint server | HTTP (HTTPS) | 5985 (5986) | Required to connect to on-premises Microsoft SharePoint organizations through the WinRM port. |
| On-premises Microsoft Exchange server | TCP | 80 or 443 | Required to connect to on-premises Microsoft Exchange organizations. |
| S3 Compatible object storage repository / IBM Cloud Object Storage / Wasabi Cloud Object Storage | TCP | 443 | Required to work with object storage repositories.  The endpoint for Azure Blob Storage is <account>.blob.core.windows.net.  The endpoints for Amazon S3 object storage repository are s3.amazonaws.com and <bucketName>.s3.<regionName>.amazonaws.com. |
| Amazon S3 object storage repository |
| Azure Blob Storage |
| Microsoft 365 | TCP | 443 | Required to connect to Microsoft 365.  The Worldwide endpoints are: graph.microsoft.com, graph.windows.net and login.microsoftonline.com.  The Microsoft 365 operated by 21 Vianet endpoints are: login.partner.microsoftonline.cn and microsoftgraph.chinacloudapi.cn. |
| SMTP server | TCP | 25 or 465 or 587 | Required to send email notifications using an SMTP server.  The Worldwide endpoint is smtp.office365.com.  The Microsoft 365 operated by 21 Vianet endpoint is smtp-legacy.partner.outlook.cn. |
| Amazon archiver appliance1 | TCP | 443 | Required to communicate with the Amazon archiver appliance. |
| TCP | 22 | Required to install the Amazon archiver appliance. |
| Azure archiver appliance1 | TCP | 443 | Required to communicate with the Azure archiver appliance. |
| TCP | 22 | Required to install the Azure archiver appliance. |
| PostgreSQL instance | TCP | 5432 (used by default) | Required to manage inbound/outbound traffic when accessing the Veeam Backup for Microsoft 365 configuration database.  Make sure to open this port on a PostgreSQL instance. |
| NATS server | TCP | 4222 (used by default) | Required to manage inbound/outbound traffic for communication between backup proxy servers within a backup proxy pool and the Veeam Backup for Microsoft 365 server.  Make sure to open this port on the NATS server. |
| Cloud gateway | Server that hosts Veeam Backup & Replication and Veeam Backup for Microsoft 365 | TCP | 9194 | Required to maintain inbound/outbound traffic. |
| Web browser | Veeam Backup for Microsoft 365 REST API | HTTPS | 4443 (used by default) | Required to connect to Restore Portal. You can also use a different port. |
| Machine with REST API | Veeam Backup for Microsoft 365 server | TCP | 9194 | Required for data exchange between Restore Portal and the Veeam Backup for Microsoft 365 server. |
| Microsoft 365 | TCP | 443 | Required for user login to Restore Portal.  The endpoint is login.microsoftonline.com (depends on a Microsoft Entra region). |

1To manage outbound traffic, TCP outgoing ports must be opened for backup proxy servers, Amazon and Azure archiver appliances. For backup proxy servers, these ports are required to access Microsoft 365 organizations and communicate with object storage repositories; for Amazon and Azure archiver appliances — to communicate with object storage repositories.

Page updated 3/24/2025

Page content applies to build 8.3.0.2201
