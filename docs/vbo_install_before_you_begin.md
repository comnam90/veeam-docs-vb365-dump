---
title: "Before You Begin"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_install_before_you_begin.html"
last_updated: "9/23/2025"
product_version: "8.3.0.2201"
---

# Before You Begin


Before you install Veeam Backup for Microsoft 365, check the following prerequisites:

* A target machine on which you plan to install Veeam Backup for Microsoft 365 must meet the system requirements. For more information, see [System Requirements](vbo_system_requirements.md#ManagementServer).
* A user account used for product installation must be a member of the local Administrators group on the target machine.
* Backup infrastructure components communicate with each other over specific ports. These ports must be open. For more information, see [Ports](vbo_used_ports.md).
* You must remove Veeam Backup for Microsoft 365 components of the product versions that are not supported by the upgrade procedure from the target machine. For more information, see [Upgrading Veeam Backup for Microsoft 365](vbo_upgrading.md). You may also need to remove earlier versions of other Veeam products and components.

Consider the following:

* For optimal performance, we recommend to install Veeam Backup for Microsoft 365 and the 3rd party components — that is a PostgreSQL instance and the NATS server, on different machines. For deployment of a PostgreSQL instance and the NATS server, we recommend to use machines with a Linux operating system installed. For more information, see [this PostgreSQL article](https://www.postgresql.org/docs/current/install-requirements.html) and [this NATS article](https://docs.nats.io/running-a-nats-service/introduction/installation#supported-operating-systems-and-architectures).
* If you do not prepare a database engine in advance, Veeam Backup for Microsoft 365 will automatically install PostgreSQL 15.14 locally on the target machine.
* It is not recommended to share a PostgreSQL instance with any other services. It should be dedicated to host the Veeam Backup for Microsoft 365 configuration database and cached metadata only.
* If you already have an installed PostgreSQL instance and want to use it for the configuration database, ensure that the LocalSystem account is added to your PostgreSQL configuration to successfully run the installation of Veeam Backup for Microsoft 365.
* If you want to use an already installed PostgreSQL instance, make sure that UTF-8 is set as the default encoding for the configuration database.
* The default PostgreSQL instance is configured to consume a minimum amount of resources, which may not be enough for Veeam Backup for Microsoft 365 performance.

When installing Veeam Backup for Microsoft 365, you can choose what PostgreSQL instance to use for the Veeam Backup for Microsoft 365 configuration database. You can use an already installed PostgreSQL instance or install a new one. If you want to install a new PostgreSQL instance using the default installation, it will be configured automatically. If you want to use an already installed PostgreSQL instance, right after you deploy Veeam Backup for Microsoft 365, ensure the instance configuration is sufficient for the product performance. For more information, see [Adjusting PostgreSQL Instance Configuration](adjust_postgres_instance.md).

* By default, the NATS server that you deploy along with Veeam Backup for Microsoft 365 on the target machine does not use the TLS encryption. To enhance security of the NATS server, we recommend that you enable the TLS encryption for the NATS server traffic. For more information, see [Enabling TLS Encryption on NATS Server](adjust_nats_instance.md).
* A PostgreSQL instance must be configured to listen for connections from all Veeam Backup for Microsoft 365 servers and backup proxy servers. You can use an already installed PostgreSQL instance or install a new one. If you want to install a new PostgreSQL instance using the default installation, it will be configured automatically. If you want to use an already installed PostgreSQL instance, specify a list of IP addresses. For more information, see [this PostgreSQL article](https://www.postgresql.org/docs/current/runtime-config-connection.html).
* If you want to use an already installed PostgreSQL instance, make sure that the pg\_trgm and plpgsql extensions are installed and enabled.
* If you want to use an existing PostgreSQL instance that was created by Veeam Backup & Replication, you must adjust the PostgreSQL configuration. For more information, see [this Veeam KB article](https://www.veeam.com/kb4638).
* Using the same NATS server for different deployments of Veeam Backup for Microsoft 365 is not supported.


