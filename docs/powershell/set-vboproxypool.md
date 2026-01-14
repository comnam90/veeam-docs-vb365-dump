---
title: "set-vboproxypool"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboproxypool.html"
last_updated: "6/28/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies settings of a backup proxy pool.

Syntax

|  |
| --- |
| Set-VBOProxyPool -Pool <VBOProxyPool> [-Name <String>] [-Description <String>] [-Proxies <VBOProxy[]>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies settings of a backup proxy pool that is added to the Veeam Backup for Microsoft 365 infrastructure. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Pool | Specifies a backup proxy pool that you want to modify. | Accepts the VBOProxyPool object.  To get this object, run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. | True | Named | True (ByValue) |
| Name | Specifies a new name of the backup proxy pool. The cmdlet will replace the current name with the specified name. | String | False | Named | False |
| Description | Specifies a description of the backup proxy pool. The cmdlet will replace the current description with the specified description. | String | False | Named | False |
| Proxies | Specifies an array of backup proxy servers. The cmdlet will add these backup proxy servers to the backup proxy pool. | Accepts the VBOProxy[] object.  To create this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOProxyPool object that contains settings of a backup proxy pool added to the Veeam Backup for Microsoft 365 backup infrastructure.

Example

Modifying Backup Proxy Pool

This example shows how change a list of backup proxy servers added to the Pool1 backup proxy pool.

|  |
| --- |
| $proxy1 = Get-VBOProxy -Hostname 172.70.53.35  $proxy2 = Get-VBOProxy -Hostname linux01  $proxy3 = Get-VBOProxy -Hostname linux02  $newproxiesArray = $proxy1,$proxy2,$proxy3  $pool = Get-VBOProxyPool -Name "Pool1"  Set-VBOProxyPool -Pool $pool -Proxies $newproxiesArray |

Perform the following steps:

1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy1 variable.
2. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy2 variable.
3. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy3 variable.
4. Set the $newproxiesArray variable value to the sequence of the $proxy1, $proxy2 and $proxy3 variables.
5. Run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. Specify the Name parameter value. Save the result to the $pool variable.
6. Run the Set-VBOProxyPool cmdlet. Set the $pool variable as the Pool parameter value. Set the $newproxiesArray variable as the Proxies parameter value.

Related Commands

* [Get-VBOProxy](get-vboproxy.md)
* [Get-VBOProxyPool](get-vboproxypool.md)

Page updated 6/28/2024

Page content applies to build 8.3.0.2201
