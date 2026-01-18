---
title: "Remove-VBOProxyPool"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vboproxypool.html"
last_updated: "12/5/2025"
product_version: "8.3.0.2201"
---

# Remove-VBOProxyPool


Short Description

Removes backup proxy pools.

Syntax

|  |
| --- |
| Remove-VBOProxyPool -Pool <VBOProxyPool> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet allows you to remove backup proxy pools from the Veeam Backup for Microsoft 365 infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Pool | Specifies a backup proxy pool. The cmdlet will remove this backup proxy pool from the Veeam Backup for Microsoft 365 infrastructure. | Accepts the [VBOProxyPool](vboproxypool.md) object.  To get this object, run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing Backup Proxy Pool from Veeam Backup for Microsoft 365 Infrastructure

This example shows how to remove a backup proxy pool with the Pool name from the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| $proxypool = Get-VBOProxyPool -Name "Pool"  Remove-VBOProxyPool -Pool $proxypool |

Perform the following steps:

1. Run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. Specify the Name parameter value. Save the result to the $proxypool variable.
2. Run the Remove-VBOProxyPool cmdlet. Set the $proxypool variable as the Pool parameter value.

Related Commands

[Get-VBOProxyPool](get-vboproxypool.md)


