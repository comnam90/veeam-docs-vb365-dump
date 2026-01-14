---
title: "vbo_proxy_pools"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_proxy_pools.html"
last_updated: "11/12/2025"
product_version: "8.3.0.2201"
---


In this article

In version 8, Veeam Backup for Microsoft 365 introduces the concept of a backup proxy pool for large-scale environments with multiple backup proxy servers. The backup proxy pool is a logical entity that groups several backup proxy servers.

As a single entity, backup proxy servers within the backup proxy pool can simultaneously process Microsoft 365 data during backup, backup copy and restore operations. This approach provides better scalability and load balancing. The backup traffic is dynamically distributed among backup proxy servers within the backup proxy pool, optimizing the backup process.

You can configure multiple backup proxy pools in the Veeam Backup for Microsoft 365 backup infrastructure. Each backup proxy pool can comprise one or more backup proxy servers. You can include a mix of Windows- and Linux-based backup proxy servers in the same backup proxy pool. You can add backup proxy servers to the backup proxy pool and remove them from the backup proxy pool at any time.

|  |
| --- |
| Note |
| Consider the following:   * The default backup proxy server cannot be added to backup proxy pools. * Each backup proxy server can only be a member of a single backup proxy pool at any given time. * You can keep remote individual backup proxy servers in the Veeam Backup for Microsoft 365 infrastructure. * Backup proxy servers within the backup proxy pool must be reachable to each other by their DNS name. |

You can associate backup proxy pools only with object storage repositories.

During the product operation, Veeam Backup for Microsoft 365 assigns various roles to backup proxy servers within a backup proxy pool. These roles required on different stages of Microsoft 365 objects processing, for example, for scheduling, creating and stopping job sessions, running backup and backup copy jobs, resolving objects, synchronization of backed-up objects metadata.

Maintenance Mode

If you want to perform service operations, you can put backup proxy servers added to a backup proxy pool in the maintenance mode. Veeam Backup for Microsoft 365 will not interrupt backup operations that are currently executed on this backup proxy pool. When a backup proxy server is put under maintenance, Veeam Backup for Microsoft 365 re-assigns execution of backup operations to another active backup proxy server within the same backup proxy pool.

For more information, see [Maintenance Mode](maintenance_mode.md).

In This Section

* [Adding Backup Proxy Pools](vbo_add_proxy_pool.md)
* [Editing Backup Proxy Pool Settings](vbo_edit_proxy_pool.md)
* [Removing Backup Proxy Pools](vbo_remove_proxy_pool.md)
* [Maintenance Mode](maintenance_mode.md)
* [Backup Proxy Pool Upgrade](vbo_upgrade_pool.md)

Page updated 11/12/2025

Page content applies to build 8.3.0.2201
