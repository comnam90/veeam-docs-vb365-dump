---
title: "Securing Veeam Backup for Microsoft 365 Infrastructure"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_securing_infrastructure.html"
last_updated: "3/2/2026"
product_version: "8.3.0.2201"
---

# Securing Veeam Backup for Microsoft 365 Infrastructure


This section includes recommendations for hardening specific Veeam Backup for Microsoft 365 components in addition to [general security considerations](vbo_general_security_considerations.md).

Infrastructure Planning

For large-scale environments, it is recommended to add the Veeam Backup for Microsoft 365 server and other components to a management domain in a separate Active Directory forest.

For medium-sized and small environments, Veeam Backup for Microsoft 365 components can be placed in a separate workgroup.

In both cases, Veeam Backup for Microsoft 365 components should be placed in a separate network where applicable.

Veeam Backup for Microsoft 365 Server

To secure the Veeam Backup for Microsoft 365 server, consider the following recommendations:

* Restrict outbound connections. To enable product update check, automatic license update, and license usage reporting, the Veeam Backup for Microsoft 365 server must be connected to the internet and be able to send requests to servers on the internet. Allow only HTTPS connections to the Veeam License Update Servers (vbo.butler.veeam.com, autolk.veeam.com), Veeam Installation Servers (download.veeam.com, download2.veeam.com), and Microsoft WSUS servers or Microsoft Update sites.
* Restrict inbound connections. Inbound connectivity to Veeam Backup for Microsoft 365 Server from the internet must not be allowed.

* Use multi-factor authentication. Enable multi-factor authentication (MFA) in the Veeam Backup for Microsoft 365 console to protect user accounts with additional user verification. For more information, see [Multi-Factor Authentication](mfa.md).
* Disable Swagger UI. If you do not require permanent access to the Swagger UI, clear the Enable Swagger UI check box in the [REST API settings](vbo_rest_api_settings.md). This reduces the potential attack surface.

* Reduce the number of user sessions opened for a long time. Set the idle timeout to automatically log off users. To do this, go to Users and Roles, select the Enable auto log off after <number> min of inactivity check box, and set the number of minutes. For more information, see [Managing Users and Roles](manage_users_roles.md#idle_timeout).

* Use the recommended Access Control List (ACL) for the custom installation folder. If you specify a custom installation folder for Veeam Backup for Microsoft 365, use the recommended ACL configuration to prevent privilege escalation and arbitrary code execution (ACE) attacks. Remove all inherited permissions from this folder. Then, add the following permissions:

* Administrators: Full control, applies to this folder, subfolders and files.
* SYSTEM: Full control, applies to this folder, subfolders and files.
* CREATOR OWNER: Full control, applies to subfolders and files only.
* Users: Read & Execute, applies to this folder, subfolders and files.

Veeam Backup for Microsoft 365 Configuration Database

The Veeam Backup for Microsoft 365 configuration database stores credentials of user accounts required to connect to various components in the Veeam Backup for Microsoft 365 infrastructure. All passwords stored in the database are encrypted. However, users that have administrator privileges on the Veeam Backup for Microsoft 365 server can decrypt passwords, which is a potential threat.

To secure the Veeam Backup for Microsoft 365 configuration database, consider the following recommendations:

* Regularly install the latest security updates for the PostgreSQL instance. To prevent a negative impact on the production environment, develop an update management strategy.

* Check that only authorized users can access the Veeam Backup for Microsoft 365 server and the server that hosts the Veeam Backup for Microsoft 365 configuration database (if the database runs on a dedicated server).
* To protect Veeam Backup for Microsoft 365 data, back up the Veeam Backup for Microsoft 365 configuration database on a regular basis. Also, make sure that the repository for the Veeam Backup for Microsoft 365 configuration database backups is not located in the same network as the Veeam Backup for Microsoft 365 server.
* Enable the TLS encryption for the PostgreSQL instance traffic. For more information, see [this PostgreSQL article](https://www.postgresql.org/docs/current/ssl-tcp.html).

Backup Repositories

To secure backup data stored in object storage repositories, use Veeam Backup for Microsoft 365 built-in encryption. For more information, see [Data Encryption](data_encryption.md).

NATS Server

To secure the NATS server, enable the TLS encryption for the NATS server traffic. For more information, see [this NATS article](https://docs.nats.io/running-a-nats-service/configuration/securing_nats/tls).


