---
title: "Supported Azure Storage Account Types"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/supported_storage_account_types.html"
last_updated: "2/27/2026"
product_version: "8.3.0.2201"
---

# Supported Azure Storage Account Types


Veeam Backup for Microsoft 365 supports different [Azure storage account types](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-overview#types-of-storage-accounts) for standard and premium performance tiers. Tables in this section list the supported storage account types.

Standard Performance Tier

The following table lists supported storage account types for Standard Performance Tier:

Standard Performance Tier

| Supported Storage Account Type | Supported Services | Supported Access Tiers |
| General-purpose V2 | Blob | Hot, Cool, Cold, Archive |
| General-purpose V1 | Blob | N/A |
| Blob Storage | Blob (block blobs and append blobs only) | Hot, Cool, Cold, Archive |

|  |
| --- |
| Note |
| Veeam Backup for Microsoft 365 uses Azure Blob Storage Archive access tier only as a target for backup copy jobs. |

Premium Performance Tier

The following table lists supported storage account types for Premium Performance Tier:

Premium Performance Tier

| Supported Storage Account Type | Supported Services | Supported Access Tiers |
| Block Blob Storage | Blob (block blobs and append blobs only) | N/A |

Related Topics

* [Azure Blob Storage Permissions](azure_archive_permissions.md)
* [Adding Microsoft Azure Blob Storage](adding_azure_storage.md)


