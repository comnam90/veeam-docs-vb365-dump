---
title: "Immutability"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/immutability.html"
last_updated: "8/30/2024"
product_version: "8.3.0.2201"
---

# Immutability


Veeam Backup for Microsoft 365 allows you to prohibit deletion of data from the object storage repository by making that data temporarily immutable and to protect data against malware activity.

You can enable data immutability when adding a new object storage repository to Veeam Backup for Microsoft 365. Object storage repository with enabled data immutability can be used to store both backups and backup copies. Once Veeam Backup for Microsoft 365 saves data to such object storage repository, data cannot be modified or deleted within the immutability period.

You can block data either for the specified number of days or for the same period as the retention period configured for the object storage repository.

|  |
| --- |
| Note |
| For Azure Blob Storage Archive access tier, Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes, you can block data only for the same period as the retention period configured for the object storage repository. You can use such object storage repositories only as a target for backup copy jobs. |

For more information, see [Adding Object Storage Repositories](adding_object_storage.md).

Data immutability has two modes: compliance and governance. By default, the compliance mode is used. When configuring the data immutability settings for a new object storage repository, you can enable the governance mode. In the governance mode, a storage administrator with specific permissions is allowed to override the lock settings and to delete the protected backups in the object storage repository. Keep in mind that for Azure Blob Storage, this means that a retention policy is unlocked on the Azure Blob Storage container.

Once enabled, data immutability cannot be disabled, but you can change the immutability period for the object storage repository where you store backups. You cannot enable data immutability later after the object storage repository is created. For more information, see [Editing Object Storage Settings](vbo_editing_repository.md#osr).

Immutability Period Extension

Depending on the object storage repository retention type, Veeam Backup for Microsoft 365 extends the immutability period in the following ways:

* If the object storage repository has the snapshot-based retention type, the duration of the immutability period for backups and backup copies stored in this object storage repository will be prolonged only for those parts of a snapshot for which retention policy still can be applied.
* If the object storage repository has the item-level retention type, the duration of the immutability period for backups and backup copies stored in this object storage repository will be prolonged only for those objects for which retention policy still can be applied.

Additional Extension of Immutability Period

|  |
| --- |
| Note |
| This is applicable only for object storage repositories with the snapshot-based retention type. |

To reduce I/O operations and associated costs, Veeam Backup for Microsoft 365 automatically adds additional days to the immutability expiration date: for object storage repositories where you store backup copies — 30 days, for object storage repositories where you store backups — 10 days.

For example, if you set the immutability period to 30 days, Veeam Backup for Microsoft 365 will add 10 days to specific objects in backup to reduce I/O operations with the storage over time. This will not affect the retention and their effective immutability. It is a background optimization. Thus, if you need 30 days immutability period, set the period to 30 days.

Additional extension of the immutability period allows Veeam Backup for Microsoft 365 to reduce the number of requests to object storage repositories, thereby you save traffic and reduce costs that can be incurred by your cloud storage provider.

Before You Begin to Use Immutability

Amazon S3 and S3 Compatible Object Storage Repositories

To use immutability for backed-up data that you want to store in Amazon S3, Amazon S3 Glacier and S3 Compatible object storage repositories, you must enable the Object Lock and Versioning features on your Amazon S3 bucket and S3 Compatible bucket at the time you create the bucket. Keep in mind that most vendors allow enabling Object Lock only at the moment of creating the bucket. Once imposed, the Object Lock prohibits deletion of data from the object storage repository until the immutability period ends.

For more information, see these Amazon articles: [Creating a bucket](https://docs.aws.amazon.com/AmazonS3/latest/userguide/create-bucket-overview.html), [Using S3 Object Lock](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock.html), [Using versioning in S3 buckets](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html).

Azure Blob Storage

If you want to use immutability for backed-up data that you want to store in Microsoft Azure Blob Storage, you must enable the data immutability settings for the object storage repository.

Do the following:

* Enable either [version-level immutability support](https://learn.microsoft.com/en-us/azure/storage/blobs/immutable-policy-configure-version-scope?tabs=azure-portal#enable-version-level-immutability-support-on-a-storage-account) or [blob versioning](https://learn.microsoft.com/en-us/azure/storage/blobs/versioning-enable?tabs=portal) for the Microsoft Azure Blob storage account.
* Make sure that the [default time-based retention policy](https://learn.microsoft.com/en-us/azure/storage/blobs/immutable-policy-configure-version-scope?tabs=azure-portal#configure-a-default-time-based-retention-policy) is not configured for the Microsoft Azure Blob storage account.
* Enable [version-level immutability support](https://learn.microsoft.com/en-us/azure/storage/blobs/immutable-policy-configure-version-scope?tabs=azure-portal#enable-version-level-immutability-for-a-new-container) for the Azure container.

For more information about immutable Microsoft Azure Blob Storage, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/storage/blobs/immutable-storage-overview).

Related Topics

* [Retention Policy](retention_policy.md)
* [Object Storage Repositories](vbo_osr.md)
* [Supported Azure Storage Account Types](supported_storage_account_types.md)
* [Supported Amazon S3 Storage Classes](supported_storage_classes_amazon.md)


