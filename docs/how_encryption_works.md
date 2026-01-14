---
title: "how_encryption_works"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/how_encryption_works.html"
last_updated: "6/10/2025"
product_version: "8.3.0.2201"
---


In this article

Veeam Backup for Microsoft 365 encrypts data before sending data to an object storage repository. Encryption is performed by Veeam Backup for Microsoft 365 Proxy Service.

The encryption process includes the following steps:

1. When you create an object storage repository, you enable encryption for this object storage and specify an encryption password to protect your data.
2. Veeam Backup for Microsoft 365 generates a backup key.
3. Veeam Backup for Microsoft 365 generates a secret key based on the specified encryption password.
4. Before sending data to the object storage repository, Veeam Backup for Microsoft 365 generates a data key to encrypt your data.
5. Veeam Backup for Microsoft 365 processes data in the following way:

1. The data key encrypts data blobs. Veeam Backup for Microsoft 365 stores the data key cryptogram next to the encrypted data blobs. By default, the value of data encrypted with a single data key is limited to 100 MB. If this limit is exceeded, Veeam Backup for Microsoft 365 generates another data key.
2. The backup key encrypts the data key.
3. The secret key encrypts the backup key.

1. Encrypted data is transferred to the target object storage repository.

Page updated 6/10/2025

Page content applies to build 8.3.0.2201
