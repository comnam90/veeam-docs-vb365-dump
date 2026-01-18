---
title: "Get-VBOProxyPool"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboproxypool.html"
last_updated: "12/5/2025"
product_version: "8.3.0.2201"
---

# Get-VBOProxyPool


Short Description

Returns backup proxy pools added to the Veeam Backup for Microsoft 365 infrastructure.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get all backup proxy pools.

|  |
| --- |
| Get-VBOProxyPool [<CommonParameters>] |

* Get a backup proxy pool by ID.

|  |
| --- |
| Get-VBOProxyPool -Id <Guid> [<CommonParameters>] |

* Get a backup proxy pool by name.

|  |
| --- |
| Get-VBOProxyPool -Name <String> [<CommonParameters>] |

Detailed Description

This cmdlet returns a list of backup proxy pools added to the Veeam Backup for Microsoft 365 backup infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Id | Specifies an ID of the backup proxy pool. The cmdlet will return the backup proxy pool with the specified ID. | Guid | True | Named | False |
| Name | Specifies a name of the backup proxy pool. The cmdlet will return the backup proxy pool with this name. | String | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOProxyPool](vboproxypool.md) object that contains settings of a backup proxy pool.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Backup Proxy Pools

|  |  |
| --- | --- |
| This command returns all backup proxy pools that are added to the Veeam Backup for Microsoft 365 infrastructure.  |  | | --- | | Get-VBOProxyPool | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Backup Proxy Pool by ID

|  |  |
| --- | --- |
| This command returns a backup proxy pool with the ID 65de3d78-0154-4e34-9848-350a1a423d87.  |  | | --- | | Get-VBOProxyPool -Id 65de3d78-0154-4e34-9848-350a1a423d87 | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Backup Proxy Pool by Name

|  |  |
| --- | --- |
| This command returns a backup proxy pool with the Pool name.  |  | | --- | | Get-VBOProxyPool -Name "Pool" | |


