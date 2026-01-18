---
title: "Get-VBOInternetProxySettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbointernetproxysettings.html"
last_updated: "1/12/2026"
product_version: "8.3.0.2201"
---

# Get-VBOInternetProxySettings


Short Description

Returns global internet proxy server settings.

Syntax

|  |
| --- |
| Get-VBOInternetProxySettings [<CommonParameters>] |

Detailed Description

This cmdlet returns global internet proxy server settings configured in Veeam Backup for Microsoft 365.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOInternetProxySettings](vbointernetproxysettings.md) object that contains internet proxy server settings.

Example

Getting Global Internet Proxy Server Settings

This command returns global internet proxy server settings.

|  |
| --- |
| Get-VBOInternetProxySettings |


