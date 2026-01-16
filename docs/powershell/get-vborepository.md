---
title: "get-vborepository"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vborepository.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns backup repositories.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get backup repositories added to Veeam Backup for Microsoft 365 by name.

|  |
| --- |
| Get-VBORepository [-Name <String>] [-LongTerm] [<CommonParameters>] |

* Get a backup repository added to Veeam Backup for Microsoft 365 by ID.

|  |
| --- |
| Get-VBORepository -Id <Guid> [<CommonParameters>] |

* Get backup repositories added to Veeam Backup for Microsoft 365 by associated backup proxy server.

|  |
| --- |
| Get-VBORepository [-Name <String>] [-LongTerm] [-Proxy <VBOProxy>] [<CommonParameters>] |

* Get backup repositories added to Veeam Backup for Microsoft 365 by associated backup proxy pool.

|  |
| --- |
| Get-VBORepository [-Name <String>] [-LongTerm] [-ProxyPool <VBOProxyPool>] [<CommonParameters>] |

Detailed Description

This cmdlet returns backup repositories added to the Veeam Backup for Microsoft 365 infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Name | Specifies a name of the backup repository. The cmdlet will return the backup repository with this name. | String | False | Named | False |
| LongTerm | Defines that the cmdlet will return settings of the following object storage repositories:   * Azure Blob Storage Archive access tier * all Amazon S3 Glacier storage classes   Default: False | SwitchParameter | False | Named | False |
| Id | Specifies an ID of the backup repository. The cmdlet will return the backup repository with this ID. | Guid | True | Named | False |
| Proxy | Specifies a backup proxy server associated with backup repositories. The cmdlet will return backup repositories that you map to this backup proxy server. | Accepts the VBOProxy object.  To get this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | False | Named | True (ByValue) |
| ProxyPool | Specifies a backup proxy pool associated with the object storage repository. The cmdlet will return the object storage repository that you map to this backup proxy pool. | Accepts the VBOProxyPool object.  To get this object, run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. | False | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBORepository object that contains settings of a backup repository.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Backup Repositories

|  |  |
| --- | --- |
| This command returns all backup repositories added to the Veeam Backup for Microsoft 365 infrastructure.  |  | | --- | | Get-VBORepository | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Repository by ID

|  |  |
| --- | --- |
| This command returns the 3cb1b56c-3396-499a-8560-ab19d510d7dd backup repository.  |  | | --- | | Get-VBORepository -Id 3cb1b56c-3396-499a-8560-ab19d510d7dd | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Repository by Name

|  |  |
| --- | --- |
| This command returns the Daily Backup backup repository.  |  | | --- | | Get-VBORepository -Name "Daily Backup" | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Getting Repositories by Name Using Wildcards

|  |  |
| --- | --- |
| This command returns backup repositories whose names start with Volume.  |  | | --- | | Get-VBORepository -Name "Volume\*" | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 5: Getting Backup Repositories Associated with Specific Backup Proxy Server

|  |  |
| --- | --- |
| This example shows how to get backup repositories associated with the d96f55a4-d15d-410b-b0f0-d51d17ccdab6 backup proxy server.  |  | | --- | | $proxy = Get-VBOProxy -Id d96f55a4-d15d-410b-b0f0-d51d17ccdab6  Get-VBORepository -Proxy $proxy |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Id parameter value. Save the result to the $proxy variable. 2. Run the Get-VBORepository cmdlet. Set the $proxy variable as the Proxy parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 6: Getting Object Storage Repositories Associated with Specific Backup Proxy Pool

|  |  |
| --- | --- |
| This example shows how to get object storage repositories associated with the 65de3d78-0154-4e34-9848-350a1a423d87 backup proxy pool.  |  | | --- | | $proxypool = Get-VBOProxyPool -Id 65de3d78-0154-4e34-9848-350a1a423d87  Get-VBORepository -ProxyPool $proxypool |  Perform the following steps:   1. Run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. Specify the Id parameter value. Save the result to the $proxypool variable. 2. Run the Get-VBORepository cmdlet. Set the $proxypool variable as the ProxyPool parameter value. |

Related Commands

* [Get-VBOProxy](get-vboproxy.md)
* [Get-VBOProxyPool](get-vboproxypool.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
