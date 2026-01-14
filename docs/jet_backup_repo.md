---
title: "jet_backup_repo"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/jet_backup_repo.html"
last_updated: "3/26/2025"
product_version: "8.3.0.2201"
---


In this article

Veeam Backup for Microsoft 365 uses JET-based backup repositories only to store backups created by backup jobs. To save data in storage systems of this type, Veeam Backup for Microsoft 365 uses Extensible Storage Engine (ESE) databases, also known as JET Blue.

You can add the following JET-based backup repositories to the Veeam Backup for Microsoft 365 backup infrastructure:

* A local directory on a backup proxy server.

A default backup repository is the C:\VeeamRepository directory on a computer with Veeam Backup for Microsoft 365.

* Direct Attached Storage (DAS) connected to the backup proxy server.
* Storage Area Network (SAN).

A backup proxy server must be connected to the SAN fabric using hardware, virtual HBA or software iSCSI initiator.

* Network Attached Storage (SMB shares version 3.0 or later).

Keep in mind that SMB shares support will be dropped in future versions of Veeam Backup for Microsoft 365.

|  |
| --- |
| Note |
| Consider the following:   * JET-based backup repositories can be connected only to remote Windows-based backup proxy servers or the default backup proxy server. Windows-based backup proxy servers must not be added to any backup proxy pool. * Veeam Backup for Microsoft 365 does not support encryption at-rest for JET-based backup repositories. * You can store your backups on volumes encrypted using the BitLocker technology if it applies to your system. After encryption, the I/O rate of the volume may change. |

In This Section

* [JET-Based Backup Repository Structure](br_structure.md)
* [Direct Attached Storage (DAS)](br_das.md)
* [Network Attached Storage (SMB Shares)](br_smb.md)
* [Adding JET-Based Backup Repositories](vbo_adding_repository.md)

Page updated 3/26/2025

Page content applies to build 8.3.0.2201
