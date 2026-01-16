---
title: "vbo_backup_proxy_servers"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_backup_proxy_servers.html"
last_updated: "4/4/2025"
product_version: "8.3.0.2201"
---


In this article

A backup proxy server is an architecture component that conducts all read and write activities during [data backup](vbo_data_backup.md), [backup copy](vbo_backup_copy.md) and [restore](vbo_data_restore.md) operations, routes backup traffic, performs data move, handles data compression and encryption and sends email notifications about backup and backup copy job results.

Consider the following:

* By default, the role of the backup proxy server is assigned to the machine where Veeam Backup for Microsoft 365 is installed. The default backup proxy server is displayed as Local backup proxy in Veeam Backup for Microsoft 365.

After you install Veeam Backup for Microsoft 365, you can configure an additional set of remote backup proxy servers and group them into backup proxy pools. You assign the role of a remote backup proxy server to a [dedicated machine](vbo_system_requirements.md#BackupProxy). This approach allows you to manage your data in a more efficient manner. For more information about backup proxy pools, see [Backup Proxy Pools](vbo_proxy_pools.md).

* A backup proxy server can be a physical or virtual machine.
* Veeam Backup for Microsoft 365 automatically installs Veeam Backup for Microsoft 365 Proxy Service on a computer that you want to use as a backup proxy server when you add a backup proxy server to the Veeam Backup for Microsoft 365 backup infrastructure. For more information, see [Adding Backup Proxy Servers](vbo_adding_proxy_server.md).
* Veeam Backup for Microsoft 365 allows you to assign a role of the backup proxy server to machines with Microsoft Windows or Linux operating systems installed.

* Veeam Backup for Microsoft 365 server and a backup proxy server must be reachable to each other by their DNS name.
* Backup proxy servers within the backup proxy pool must be reachable to each other by their DNS name.

* Veeam Backup for Microsoft 365 allows you to deploy the following types of Windows-based backup proxy servers:

* Domain backup proxy
* Workgroup backup proxy

For more information, see [Deployment Scenarios for Windows-based Backup Proxy Servers](#deployment).

* Veeam Backup for Microsoft 365 supports adding Linux-based backup proxy servers that can be non-domain and domain.
* Each backup proxy server can process one or several organizations.
* An organization can be processed by one or several backup proxy servers.
* A remote Linux-based backup proxy server can be associated only with object storage repositories.
* A remote Windows-based backup proxy server and the default backup proxy server can be associated with object storage repositories and JET-based backup repositories.
* A backup proxy server is responsible for sending email notifications about backup and backup copy job results.

For more information on how to configure email notification settings, see [Notification Settings](vbo_notification_settings.md).

* For each backup proxy server, Veeam Backup for Microsoft 365 saves information about restore points to the configuration database created on the PostgreSQL instance. Veeam Backup for Microsoft 365 collects this information from all backup repositories associated with this backup proxy server.

Deployment Scenarios for Windows-based Backup Proxy Servers

Veeam Backup for Microsoft 365 offers the following deployment scenarios for a Windows-based backup proxy server:

* Domain backup proxy

In this scenario, a machine used as a backup proxy server resides in the same domain as the Veeam Backup for Microsoft 365 server or in a trusted domain. To establish a connection with a domain backup proxy, Veeam Backup for Microsoft 365 uses credentials that you provide when you add a backup proxy server to the Veeam Backup for Microsoft 365 infrastructure.

* Workgroup backup proxy

In this scenario, a machine used as a backup proxy server resides in a workgroup. To establish a connection with a workgroup backup proxy, Veeam Backup for Microsoft 365 uses an SSL certificate. For more information, see [Security Settings](vbo_security_settings.md).

You can deploy the Veeam Backup for Microsoft 365 server and backup proxy servers across various combinations of workgroups and domains. Keep in mind that if the Veeam Backup for Microsoft 365 server is deployed in a particular domain, the backup proxy servers can be located in a different domain or even across multiple domains.

In This Section

* [Adding Backup Proxy Servers](vbo_adding_proxy_server.md)
* [Editing Backup Proxy Server Settings](vbo_editing_proxy_server.md)
* [Rescanning Backup Proxy Servers](vbo_rescanning_proxy_server.md)
* [Upgrading Backup Proxy Servers](vbo_upgrading_proxy_server.md)
* [Removing Backup Proxy Servers](vbo_removing_proxy_server.md)
* [Modifying Backup Proxy Server Properties](vbo_modifying_proxy_server.md)

Page updated 4/4/2025

Page content applies to build 8.3.0.2201
