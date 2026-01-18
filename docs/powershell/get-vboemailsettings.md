---
title: "Get-VBOEmailSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboemailsettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Get-VBOEmailSettings


Short Description

Returns email notification settings. Email notifications are sent from a backup proxy server upon each execution of a backup or backup copy job.

Syntax

|  |
| --- |
| Get-VBOEmailSettings [<CommonParameters>] |

Detailed Description

This cmdlet returns email notification settings configured for Veeam Backup for Microsoft 365.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOEmailSettings](vboemailsettings.md) object that contains email notification settings.

Example

Getting Email Notification Settings

This command returns email notification settings.

|  |
| --- |
| Get-VBOEmailSettings |


