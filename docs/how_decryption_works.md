---
title: "how_decryption_works"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/how_decryption_works.html"
last_updated: "10/29/2024"
product_version: "8.3.0.2201"
---


In this article

When you access backed-up data stored in an object storage repository with the encryption option enabled, Veeam Backup for Microsoft 365 automatically decrypts your data in the background. Decryption is performed by Veeam Backup for Microsoft 365 Proxy Service.

The decryption process includes the following steps:

1. Veeam Backup for Microsoft 365 reads the data key cryptogram next to the encrypted data blobs that you access.
2. Using the backup key ID stored in the data key, Veeam Backup for Microsoft 365 obtains the backup key.
3. Veeam Backup for Microsoft 365 applies the secret key to decrypt the backup key. If needed, Veeam Backup for Microsoft 365 decrypts a chain of backup keys. For more information, see [Encryption Password Change](data_encryption.md#epass_change).
4. The backup key unlocks underlying data keys.
5. Data keys decrypt data blobs.

Page updated 10/29/2024

Page content applies to build 8.3.0.2201
