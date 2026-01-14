---
title: "get-vboencryptionkey"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboencryptionkey.html"
last_updated: "10/2/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns encryption keys.

Syntax

|  |
| --- |
| Get-VBOEncryptionKey [-Id <Guid>] [-Description <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of encryption keys for object storage repositories.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Id | Specifies an ID of the encryption key. The cmdlet will return the encryption key with this ID. | Guid | False | Named | False |
| Description | Specifies a description of the encryption key. The cmdlet will return the encryption key with this description.  Note: To filter objects, you can use \* and ? wildcard characters. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOEncryptionKey object that contains settings of an encryption key.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Encryption Keys

|  |  |
| --- | --- |
| This command returns all encryption keys managed by Veeam Backup for Microsoft 365.  |  | | --- | | Get-VBOEncryptionKey | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Encryption Keys with Specified ID

|  |  |
| --- | --- |
| This command returns the 8657138e-ca49-4f91-a8ec-a17818eb818e encryption key.  |  | | --- | | Get-VBOEncryptionKey -Id 8657138e-ca49-4f91-a8ec-a17818eb818e | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Encryption Keys with Specified Description

|  |  |
| --- | --- |
| This command returns all encryption keys with the specified description.  |  | | --- | | Get-VBOEncryptionKey -Description "Veeam Admin Key" | |

Page updated 10/2/2025

Page content applies to build 8.3.0.2201
