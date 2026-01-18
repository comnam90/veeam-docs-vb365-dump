---
title: "Get-VBOAzureBlobAccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboazureblobaccount.html"
last_updated: "12/22/2025"
product_version: "8.3.0.2201"
---

# Get-VBOAzureBlobAccount


Short Description

Returns Microsoft Azure Blob Storage account credentials.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get Microsoft Azure Blob Storage account credentials by the credentials login name.

|  |
| --- |
| Get-VBOAzureBlobAccount [-Name <String>] [<CommonParameters>] |

* Get Microsoft Azure Blob Storage account credentials by the credentials ID.

|  |
| --- |
| Get-VBOAzureBlobAccount -Id <Guid> [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of storage account credentials for Microsoft Azure Blob Storage added to Veeam Backup for Microsoft 365.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Name | Specifies an array of login names for Microsoft Azure Blob Storage account credentials. The cmdlet will return Microsoft Azure Blob Storage account credentials with these login names. | String | False | Named | False |
| Id | Specifies an array of IDs for Microsoft Azure Blob Storage account credentials. The cmdlet will return Microsoft Azure Blob Storage account credentials with these IDs. | Guid | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAzureBlobAccount](vboazureblobaccount.md) object that contains storage account credentials for Microsoft Azure Blob Storage.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Microsoft Azure Blob Storage Credentials Record by Name

|  |  |
| --- | --- |
| This command returns the Microsoft Azure Blob Storage account credentials by the storage account credentials login name.  |  | | --- | | Get-VBOAzureBlobAccount -Name "Microsoft Azure Blob" | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Microsoft Azure Blob Storage Credentials Record by ID

|  |  |
| --- | --- |
| This command returns the Microsoft Azure Blob Storage account credentials by the storage account credentials ID.  |  | | --- | | Get-VBOAzureBlobAccount -Id 936edf7c-7cf3-4ddc-9895-c7485ef4bb2c | |


