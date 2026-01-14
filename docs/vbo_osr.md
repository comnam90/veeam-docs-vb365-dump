---
title: "vbo_osr"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_osr.html"
last_updated: "5/9/2025"
product_version: "8.3.0.2201"
---


In this article

Veeam Backup for Microsoft 365 uses object storage repositories to store backups and backup copies created for Microsoft 365 and on-premises Microsoft organizations. Veeam Backup for Microsoft 365 supports the following cloud and on-premises storage systems:

* S3 Compatible object storage

Any S3 Compatible object storage device fully compatible with the AWS S3 operations and AWS S3 Signature Version 4 standard.

* Amazon S3 object storage

For more information about Amazon S3 object storage, see [this Amazon article](https://aws.amazon.com/s3/?sc_channel=PS&sc_campaign=acquisition_RU&sc_publisher=google&sc_medium=ACQ-P%7CPS-GO%7CBrand%7CDesktop%7CSU%7CStorage%7CS3%7CRU%7CEN%7CText&sc_content=s3_e&sc_detail=amazon%20s3&sc_category=Storage&sc_segment=293618441715&sc_matchtype=e&sc_country=RU&s_kwcid=AL!4422!3!293618441715!e!!g!!amazon%20s3&ef_id=EAIaIQobChMI19fJ5IP75AIVQeWaCh0lyAGdEAAYASAAEgIHnPD_BwE:G:s). For more information about Amazon S3 storage classes that Veeam Backup for Microsoft 365 supports, see [Supported Amazon S3 Storage Classes](supported_storage_classes_amazon.md). For more information about required permissions, see [Amazon S3 Storage Permissions](amazon_s3_permissions.md).

* Microsoft Azure Blob storage

For more information about Microsoft Azure Blob storage, see [this Microsoft article](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction). For more information about Azure storage account types that Veeam Backup for Microsoft 365 supports, see [Supported Azure Storage Account Types](supported_storage_account_types.md). For more information about Azure Blob storage permissions, see [Azure Blob Storage Permissions](azure_archive_permissions.md).

* IBM Cloud Object Storage

For more information about IBM Cloud Object Storage, see [this IBM article](https://www.ibm.com/cloud/object-storage?cm_mmc=Search_Google-_-Hybrid+Cloud_Cloud+Platform+Digital-_-WW_ICE-_-ibm%20cloud%20object%20storage_e&cm_mmca1=000016GC&cm_mmca2=10007090&cm_mmca7=9047071&cm_mmca8=aud-635498184938:kwd-320507222281&cm_mmca9=EAIaIQobChMI8eGwjfnF5QIVxRsYCh1ifwoSEAAYASAAEgLyofD_BwE&cm_mmca10=376281732194&cm_mmca11=e&gclid=EAIaIQobChMI8eGwjfnF5QIVxRsYCh1ifwoSEAAYASAAEgLyofD_BwE&gclsrc=aw.ds).

* Wasabi Cloud Object Storage

For more information about Wasabi Cloud Object Storage, see [this Wasabi article](https://wasabi.com/solutions/#cloud-strategy).

The following table lists supported object storage depending on vendor and purpose of usage:

| Vendor | Access tier / Storage class | Data backup | Backup copy |
| --- | --- | --- | --- |
| Azure Blob Storage | Hot | ✔ | ✔ |
| Cool | ✔ | ✔ |
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

Object Storage Usage Scenarios

Veeam Backup for Microsoft 365 offers the following usage scenarios for object storage repositories:

* Data backup. In this scenario, you create a backup job to back up your data directly to the supported cloud or on-premises storage system. This is not applicable to Azure Blob Storage Archive access tier and all Amazon S3 Glacier storage classes.

You specify a target object storage repository for a backup job at the [Specify Backup Repository](specify_backup_proxy_server.md) step. During a backup job, data is compressed and backed up directly to the object storage repository. To save cache with backup metadata, Veeam Backup for Microsoft 365 uses the PersistentCache database created by Veeam Backup for Microsoft 365 on the PostgreSQL instance. Metadata is saved separately for each object storage repository to the file located by default in the C:\Program Files\PostgreSQL\15\data folder on a machine with the PostgreSQL instance. For more information, see [Cache](understanding_cache.md).

* Backup copy. In this scenario, you create a backup copy job to transfer your backed-up data as backup copies from one object storage repository to another. For more information, see [Getting Started with Backup Copy](get_started_backup_copy.md).

|  |
| --- |
| Note |
| Veeam Backup for Microsoft 365 supports Azure Blob Storage Archive access tier, Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes only as a target for backup copy jobs. |

Data Protection

Veeam Backup for Microsoft 365 allows you to prohibit deletion of data from the object storage repository by making that data temporarily immutable and to protect data against malware activity. To do this, you need to enable immutability when adding an object storage repository to Veeam Backup for Microsoft 365. For more information, see [Immutability](immutability.md).

Data Validation

Veeam Backup for Microsoft 365 provides a self-check mechanism that allows the product to validate if backed-up data appears in the object storage repository uncorrupted after compression and transfer.

The process of data validation involves the following steps:

1. Before sending data to the object storage repository, Veeam Backup for Microsoft 365 calculates hash: for Amazon S3 object storage repositories and S3 Compatible object storage repositories both the MD5 and SHA256 checksums are calculated, for Microsoft Azure Blob storage — the MD5 checksum only.
2. When the backed-up data appears in the object storage repository, checksums are calculated again and are compared with values obtained before data was sent to this object storage repository.

|  |
| --- |
| Note |
| Different checksums mean that data was corrupted during transfer to the object storage repository. Such data will not be saved to this object storage repository. Veeam Backup for Microsoft 365 will try to resend data to this object storage repository. |

In This Section

* [Object Storage Repository Structure](object_storage_structure.md)
* [Cache](understanding_cache.md)
* [Compression](understanding_compression.md)
* [Data Encryption](data_encryption.md)
* [Immutability](immutability.md)
* [Adding Object Storage Repositories](adding_object_storage.md)

Page updated 5/9/2025

Page content applies to build 8.3.0.2201
