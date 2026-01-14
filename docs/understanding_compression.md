---
title: "understanding_compression"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/understanding_compression.html"
last_updated: "8/23/2024"
product_version: "8.3.0.2201"
---


In this article

Compression in Veeam Backup for Microsoft 365 helps you save storage space and reduce costs incurred by your cloud storage provider for maintaining backup data in object storage repositories.

Compression works in the following way:

* All chunks of data that are larger than 512 bytes are subject to compression; each blob file that is created is compressed first and then saved to object storage.

To compress data, Veeam Backup for Microsoft 365 uses the ZSTD algorithm. For more information about this algorithm, see [this Zstandard article](http://facebook.github.io/zstd/).

* Compression is performed by Veeam Backup for Microsoft 365 Proxy Service.
* Certain types of data such as images or other media files cannot be compressed properly. Thereby an output compressed blob file becomes larger than it could be if it was not compressed at all. In such a scenario, the uncompressed version of the file will be saved.

Related Topics

* [Backup Proxy Servers](vbo_backup_proxy_servers.md)
* [Backup Proxy Pools](vbo_proxy_pools.md)

Page updated 8/23/2024

Page content applies to build 8.3.0.2201
