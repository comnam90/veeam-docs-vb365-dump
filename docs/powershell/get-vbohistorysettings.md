---
title: "Get-VBOHistorySettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbohistorysettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Get-VBOHistorySettings


Short Description

Returns history settings for backup and backup copy job sessions.

Syntax

|  |
| --- |
| Get-VBOHistorySettings [<CommonParameters>] |

Detailed Description

This cmdlet returns job session history settings stored in Veeam Backup for Microsoft 365.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOHistorySettings](vbohistorysettings.md) object that contains history settings for backup and backup copy job sessions.

Example

Getting Job Session History Settings

This command returns job session history settings.

|  |
| --- |
| Get-VBOHistorySettings |


