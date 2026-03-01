---
title: "Backup Copy"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_backup_copy.html"
last_updated: "2/27/2026"
product_version: "8.3.0.2201"
---

# Backup Copy


To enhance protection of your data against disasters, you can extend your backup jobs with backup copy capabilities. With backup copy, you can transfer backups created by backup jobs from a source backup repository to target backup repository for long-term storage.

Both source and target backup repositories for backup copy must be object storage repositories. They must be associated with the same backup proxy server or backup proxy pool and have the same retention type. For more information on how to add object storage repositories, see [Adding Object Storage Repositories](adding_object_storage.md).

|  |
| --- |
| Note |
| Veeam Backup for Microsoft 365 does not support JET-based backup repositories as source or target backup repositories for backup copy. For more information, see [JET-Based Backup Repositories](jet_backup_repo.md). |

As well as backup, backup copy is a job-driven process. You can create a backup copy job right after configuring a backup job or at any time later. Keep in mind that object storage repository that you selected as a target for your backup job becomes a source backup repository for backup copies. A target object storage repository to store backup copies must be specified when you configure a backup copy job. For more information, see [Creating Backup Copy Job](vbo_new_copy_job.md).

The following table lists cloud and on-premises storage systems that Veeam Backup for Microsoft 365 supports as a source and target for backup copy jobs:

Backup Copy

| Vendor | Access tier / Storage class | Source for backup copy | Target for backup copy |
| Azure Blob Storage | Hot | ✔ | ✔ |
| Cool | ✔ | ✔ |
| Cold | ✔ | ✔ |
| Archive |  | ✔ |
| Amazon S3 Storage | Standard | ✔ | ✔ |
| Standard-Infrequent Access | ✔ | ✔ |
| One Zone-Infrequent Access | ✔ | ✔ |
| Glacier Instant Retrieval |  | ✔ |
| Glacier Flexible Retrieval |  | ✔ |
| Glacier Deep Archive |  | ✔ |
| IBM Cloud Object Storage | | ✔ | ✔ |
| Wasabi Cloud Object Storage | | ✔ | ✔ |
| Other S3 Compatible (if applicable) | | ✔ | ✔ |

Storage format of backup copies differs from storage format of backups: maximum size of blob files increases from 5 MB for backups to 256 MB for backup copies. Repacking of backed-up data is performed by either a backup proxy server or an auxiliary archiver appliance that Veeam Backup for Microsoft 365 can create in Microsoft Azure or Amazon EC2. Processing larger blobs helps you reduce costs incurred by your cloud storage provider for retrieving backed-up data from backup copies.

Veeam Backup for Microsoft 365 allows you to prohibit deletion of data from the object storage repository by making that data temporarily immutable and to protect data against malware activity. For more information about protecting data in backup copies, see [Immutability](immutability.md).

In This Section

* [Getting Started with Backup Copy](get_started_backup_copy.md)
* [How Backup Copy Works](how_backup_copy_works.md)
* [Creating Backup Copy Job](vbo_new_copy_job.md)
* [Managing Backup Copy Jobs](managing_backup_copy_jobs.md)
* [Retrieving Backed-Up Data](retrieving_backed_up_files.md)


