---
title: "VBOHistorySettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbohistorysettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOHistorySettings


Contains details about history settings for backup and backup copy job sessions.

| Property | Type | Description |
| --- | --- | --- |
| KeepAllSessions | Bool | If True, Veeam Backup for Microsoft 365 keeps backup and backup copy job sessions forever. |
| KeepOnlyLastXweeks | Int | Number of weeks during which backup and backup copy job sessions are kept. |

Related Commands

* [Get-VBOHistorySettings](get-vbohistorysettings.md)
* [Set-VBOHistorySettings](set-vbohistorysettings.md)


