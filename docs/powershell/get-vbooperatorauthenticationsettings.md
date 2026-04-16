---
title: "Get-VBOOperatorAuthenticationSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbooperatorauthenticationsettings.html"
last_updated: "3/12/2026"
product_version: "8.4.0.1457"
---

# Get-VBOOperatorAuthenticationSettings


Short Description

Returns restore operator authentication settings.

Syntax

|  |
| --- |
| Get-VBOOperatorAuthenticationSettings [<CommonParameters>] |

Detailed Description

This cmdlet returns restore operator authentication settings. These settings specify a TLS certificate used to establish connection with the Veeam Backup for Microsoft 365 server.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Getting Restore Operator Authentication Settings

This command returns restore operator authentication settings.

|  |
| --- |
| Get-VBOOperatorAuthenticationSettings |


