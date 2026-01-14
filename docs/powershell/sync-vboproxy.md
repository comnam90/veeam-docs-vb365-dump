---
title: "sync-vboproxy"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/sync-vboproxy.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Rescans backup proxy servers.

Syntax

This cmdlet provides parameter sets that allow you to:

* Rescan all backup proxy servers added to Veeam Backup for Microsoft 365 configuration.

|  |
| --- |
| Sync-VBOProxy [<CommonParameters>] |

* Rescan a specific backup proxy server.

|  |
| --- |
| Sync-VBOProxy [-Proxy <VBOProxy[]>] [<CommonParameters>] |

Detailed Description

This cmdlet rescans backup proxy servers added to Veeam Backup for Microsoft 365. You can either rescan all backup proxy servers or rescan a specific backup proxy server.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Proxy | Specifies an array of backup proxy servers added to Veeam Backup for Microsoft 365. The cmdlet will rescan the specified backup proxy servers. | Accepts the VBOProxy[] object.  To get this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | False | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Rescanning All Backup Proxy Servers

|  |  |
| --- | --- |
| This command rescans all backup proxy servers added to Veeam Backup for Microsoft 365.  |  | | --- | | Sync-VBOProxy | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Rescanning Specific Backup Proxy Servers

|  |  |
| --- | --- |
| This example shows how to rescan backup proxy servers with the 172.17.53.53 and 172.17.51.60 IP addresses.  |  | | --- | | $proxy1 = Get-VBOProxy -Hostname 172.17.53.53  $proxy2 = Get-VBOProxy -Hostname 172.17.51.60  Sync-VBOProxy -Proxy ($proxy1, $proxy2) |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy1 variable. 2. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy2 variable. 3. Run the Sync-VBOProxy cmdlet. Set the $proxy1 and $proxy2 variables as the Proxy parameter value. |

Related Commands

[Get-VBOProxy](get-vboproxy.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
