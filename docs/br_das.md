---
title: "Direct Attached Storage (DAS)"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/br_das.html"
last_updated: "7/17/2024"
product_version: "8.3.0.2201"
---

# Direct Attached Storage (DAS)


In Veeam Backup for Microsoft 365, you can use the following Microsoft Windows and Linux-based storage types as JET-based backup repositories:

* A Windows-based server with local or directly attached storage.

Such storage can be a local disk, directly attached disk-based storage (such as a USB hard drive), or iSCSI/FC SAN LUN in case the server is connected into the SAN fabric.

* Linux-based storage connected to the Veeam Backup for Microsoft 365 server.

Such storage can be a local disk, directly attached disk-based storage (such as a USB hard drive), NFS share, or iSCSI/FC SAN LUN in case the server is connected into the SAN fabric. The storage must then be provisioned to the Windows-based host as a volume in the guest OS.

Related Topics

[Adding JET-Based Backup Repositories](vbo_adding_repository.md)


