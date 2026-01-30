---
title: "Supported Amazon S3 Storage Classes"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/supported_storage_classes_amazon.html"
last_updated: "11/12/2025"
product_version: "8.3.0.2201"
---

# Supported Amazon S3 Storage Classes


Veeam Backup for Microsoft 365 supports the following [Amazon S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/):

* Amazon S3 Standard (S3 Standard)

Use this storage class for general-purpose storage of frequently accessed data. Veeam Backup for Microsoft 365 supports this storage class as a target for both backup and backup copy jobs.

* Amazon S3 Standard-Infrequent Access (S3 Standard-IA)

Use this storage class for long-lived, but less frequently accessed data. Veeam Backup for Microsoft 365 supports this storage class as a target for both backup and backup copy jobs.

* Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA)

Use this storage class for storing data that is accessed less frequently, but requires rapid access when needed. S3 One Zone-IA stores data cost-effectively in a single availability zone. Keep in mind that data will be lost in the event of a failure or the destruction of this availability zone. Veeam Backup for Microsoft 365 supports this storage class as a target for both backup and backup copy jobs. For example, you can use this storage class for storing secondary backup copies of on-premises data or easily re-creatable data.

* Amazon S3 Glacier Instant Retrieval (S3 Glacier Instant Retrieval)

Use this storage class for storing data that is regularly accessed and requires data retrieval in milliseconds. Veeam Backup for Microsoft 365 supports this storage class only as a target for backup copy jobs.

* Amazon S3 Glacier Flexible Retrieval (S3 Glacier Flexible Retrieval)

Use this storage class for storing data that is accessed 1–2 times per year and is retrieved asynchronously. Veeam Backup for Microsoft 365 supports this storage class only as a target for backup copy jobs.

* Amazon S3 Glacier Deep Archive (S3 Glacier Deep Archive)

Use this storage class for storing data that may be rarely accessed. Veeam Backup for Microsoft 365 supports this storage class only as a target for backup copy jobs.

Related Topics

* [Amazon S3 Storage Permissions](amazon_s3_permissions.md)
* [Adding Amazon S3 Object Storage Repositories](adding_amazon_s3_storage.md)


