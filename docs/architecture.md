---
title: "Veeam Backup for Microsoft 365 Architecture"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/architecture.html"
last_updated: "9/16/2025"
product_version: "8.3.0.2201"
---

# Veeam Backup for Microsoft 365 Architecture


Veeam Backup for Microsoft 365 architecture includes the following core structural components — Veeam Backup for Microsoft 365 server, backup proxy server and backup repository, and additional components such as REST API along with Restore Portal and PowerShell.

The NATS server and a PostgreSQL instance are important 3rd party components that provide centralized management for the Veeam Backup for Microsoft 365 operation.

Veeam Backup for Microsoft 365 Server

Veeam Backup for Microsoft 365 server is responsible for setting up and managing other backup infrastructure components, jobs scheduling and task coordination. As part of Veeam Backup for Microsoft 365 server, the following components are installed:

* Services:

* Veeam Backup for Microsoft 365 Service

Coordinates all operations performed by the product, adds and manages other backup infrastructure components as well as controls global settings for the backup infrastructure.

* Veeam Backup for Microsoft 365 Proxy Service

Manages backup proxy servers and backup repositories.

* Veeam Backup for Microsoft 365 REST API Service

Processes REST API commands.

Restore Portal is deployed along with REST API on the same machine. Restore Portal is a web-based solution for self-service restore of backed-up data. Restore Portal uses REST API to communicate with the Veeam Backup for Microsoft 365 server. For more information, see [Data Restore Using Restore Portal](ssp_restore.md).

* Veeam Backup for Microsoft 365 Console

Provides an interface that allows users to interact with the Veeam Backup for Microsoft 365 server and backup infrastructure components.

* Veeam Backup for Microsoft 365 PowerShell toolkit

Includes sets of PowerShell cmdlets and allows you to run Veeam Backup for Microsoft 365 PowerShell sessions.

* Veeam Explorers

Set of instruments that comes as part of Veeam Backup for Microsoft 365 and allows you to restore or export your data from backups.

Backup Proxy Server

A backup proxy server is an architecture component that conducts all read and write activities during data backup, backup copy and restore operations, routes backup traffic, performs data move, handles data compression and encryption and sends email notifications about backup and backup copy job results.

For more information, see [Backup Proxy Servers](vbo_backup_proxy_servers.md).

Backup Proxy Pool

A backup proxy pool is a logical entity that you configure to group several backup proxy servers. Using backup proxy pools provides better scalability and load balancing.

For more information, see [Backup Proxy Pools](vbo_proxy_pools.md).

NATS Server

The NATS server ensures communication between backup proxy servers that you group into a backup proxy pool. For more information about backup proxy pools, see [Backup Proxy Pools](vbo_proxy_pools.md).

During the Veeam Backup for Microsoft 365 installation, you can either deploy a new NATS server instance or use an already installed NATS server instance. For more information, see [Installing Veeam Backup for Microsoft 365](vbo_installing_vbo.md) and [Upgrading Veeam Backup for Microsoft 365](vbo_upgrading.md).

The NATS server uses the JetStream technology that provides message queuing and streaming capabilities. Veeam Backup for Microsoft 365 leverages this technology to create a set of streams that provide communication between the backup infrastructure components.

For more information about JetStream, see [this NATS article](https://docs.nats.io/nats-concepts/jetstream).

PostgreSQL Instance

A PostgreSQL instance hosts a centralized configuration database that is used by Veeam Backup for Microsoft 365 components, including backup proxy servers. Data is saved to the file with the VeeamBackup365 name located by default in the C:\Program Files\PostgreSQL\15\data folder on a machine with the PostgreSQL instance.

During the Veeam Backup for Microsoft 365 installation, you can either deploy a new PostgreSQL instance or use an already installed PostgreSQL instance. For more information, see [Installing Veeam Backup for Microsoft 365](vbo_installing_vbo.md) and [Upgrading Veeam Backup for Microsoft 365](vbo_upgrading.md).

Backup Repository

A backup repository is a storage system within the backup infrastructure where Veeam Backup for Microsoft 365 saves backups and backup copies.

Veeam Backup for Microsoft 365 supports JET-based backup repositories and object storage repositories.

For more information, see [Backup Repositories](vbo_backup_repositories.md).

Related Topics

* [System Requirements](vbo_system_requirements.md)
* [Ports](vbo_used_ports.md)
* [Installing Veeam Backup for Microsoft 365](vbo_installing_vbo.md)
* [Installing REST API](vbo_installing_rest.md)


