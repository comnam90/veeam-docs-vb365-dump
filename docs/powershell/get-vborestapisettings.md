---
title: "Get-VBORestAPISettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vborestapisettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Get-VBORestAPISettings


Short Description

Returns REST API settings.

Syntax

|  |
| --- |
| Get-VBORestAPISettings [<CommonParameters>] |

Detailed Description

This cmdlet returns REST API settings. These settings are used by Veeam Backup for Microsoft 365 REST API Service.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBORestAPISettings](vborestapisettings.md) object that contains REST API settings.

Example

Getting REST API Settings

This command returns the Veeam Backup for Microsoft 365 REST API settings.

|  |
| --- |
| Get-VBORestAPISettings |


