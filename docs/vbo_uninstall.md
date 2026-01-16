---
title: "vbo_uninstall"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_uninstall.html"
last_updated: "11/12/2025"
product_version: "8.3.0.2201"
---


In this article

To uninstall Veeam Backup for Microsoft 365, do the following:

1. Stop all restore sessions (if any) in Veeam Explorer for Microsoft Exchange, Veeam Explorer for Microsoft SharePoint, Veeam Explorer for Microsoft OneDrive for Business and Veeam Explorer for Microsoft Teams.
2. Open the Veeam Backup for Microsoft 365 console, go to Backup Infrastructure > Backup Proxies and remove all configured backup proxy servers. For more information, see [Removing Backup Proxy Servers](vbo_removing_proxy_server.md).
3. From the Start menu, select Control Panel > Programs and Features.
4. In the programs list, right-click Veeam Backup for Microsoft 365 and select Uninstall.

The Veeam Backup for Microsoft 365 uninstallation wizard runs.

1. At the Uninstall step, select check boxes next to the items that you want to uninstall and click Remove. Keep in mind that the Veeam Backup for Microsoft 365 uninstallation wizard uninstalls Veeam Explorers that are included in the Veeam Backup for Microsoft 365 installation package if you have only Veeam Backup for Microsoft 365 on your machine.
2. Wait for the uninstallation process to complete and click Finish to exit the wizard.

[![Uninstalling Veeam Backup for Microsoft 365](images/vbo_iso_uninstall.webp)](images/vbo_iso_uninstall.webp "Uninstalling Veeam Backup for Microsoft 365")

Removing Veeam Backup for Microsoft 365 Data from PostgreSQL Instance and NATS Server

During the uninstallation process, Veeam Backup for Microsoft 365 does not remove automatically the product data from a PostgreSQL instance and the NATS server. You can manually remove data related to Veeam Backup for Microsoft 365: the configuration database, streams and configuration files.

The configuration database file with the VeeamBackup365 name and configuration files are located in the C:\Program Files\PostgreSQL\15\data folder on a machine with the PostgreSQL instance.

Streams related to Veeam Backup for Microsoft 365 are located in the %ProgramData%\Veeam\Backup365\nats folder on the Veeam Backup for Microsoft 365 server.

The NATS server configuration files are located in the %ProgramData%\NATS folder.

For more information on how to remove the configuration database, see [this PostgreSQL article](https://www.postgresql.org/docs/16/sql-dropdatabase.html).

For more information on how to delete streams, see [this NATS article](https://docs.nats.io/running-a-nats-service/nats_admin/jetstream_admin/streams#deleting-all-data).

For more information on how to delete the nats-server service, see [this NATS article](https://docs.nats.io/running-a-nats-service/introduction/windows_srv) and [this Microsoft article](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/sc-delete).

Page updated 11/12/2025

Page content applies to build 8.3.0.2201
