---
title: "add-vboproxypool"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboproxypool.html"
last_updated: "2/20/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Adds a backup proxy pool to the Veeam Backup for Microsoft 365 infrastructure.

Syntax

|  |
| --- |
| Add-VBOProxyPool -Name <String> [-Description <String>] -Proxies <VBOProxy[]> [<CommonParameters>] |

Detailed Description

This cmdlet adds a backup proxy pool to the Veeam Backup for Microsoft 365 backup infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Name | Specifies a name of the backup proxy pool. The cmdlet will create a backup proxy pool with this name. | String | True | Named | False |
| Description | Specifies a description of the backup proxy pool.  The default description contains information on the user who added the backup proxy pool, date and time when the backup proxy pool was added. | String | False | Named | False |
| Proxies | Specifies an array of backup proxy servers. The cmdlet will add these backup proxy servers to the backup proxy pool. | Accepts the VBOProxy[] object.  To create this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOProxyPool object that contains settings of a backup proxy pool added to the Veeam Backup for Microsoft 365 backup infrastructure.

Example

Adding Backup Proxy Pool

This example shows how to add a backup proxy pool to the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| $proxy1 = Get-VBOProxy -Hostname 172.70.53.53  $proxy2 = Get-VBOProxy -Hostname linux01  Add-VBOProxyPool -Name "Pool1" -Proxies ($proxy1, $proxy2) |

Perform the following steps:

1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy1 variable.
2. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy2 variable.
3. Run the Add-VBOProxyPool cmdlet. Specify the Name parameter value. Set the $proxy1 and $proxy2 variables as the Proxies parameter value.

Related Commands

[Get-VBOProxy](get-vboproxy.md)

Page updated 2/20/2025

Page content applies to build 8.3.0.2201
