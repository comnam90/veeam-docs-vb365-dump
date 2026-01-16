---
title: "set-vbohistorysettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbohistorysettings.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies history settings for backup and backup copy job sessions.

Syntax

This cmdlet provides parameter sets that allow you to:

* Modify session history settings in weeks.

|  |
| --- |
| Set-VBOHistorySettings -KeepOnlyLastXweeks <Int32> [<CommonParameters>] |

* Modify session history settings to keep job sessions in Veeam Backup for Microsoft 365 forever.

|  |
| --- |
| Set-VBOHistorySettings [-KeepAllSessions] [<CommonParameters>] |

Detailed Description

This cmdlet modifies the job session history settings. By default, Veeam Backup for Microsoft 365 will keep job sessions forever.

To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| KeepOnlyLastXweeks | Specifies the retention period for job sessions (weeks).  Default: 53 | Int32 | True | Named | False |
| KeepAllSessions | Defines that Veeam Backup for Microsoft 365 will keep job sessions forever.  Default: False | SwitchParameter | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Setting Job Session Retention Period

|  |  |
| --- | --- |
| This command sets job session retention period in weeks.  |  | | --- | | Set-VBOHistorySettings -KeepOnlyLastXweeks 1 | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Keeping Job Sessions Forever

|  |  |
| --- | --- |
| This command configures Veeam Backup for Microsoft 365 to keep job sessions forever.  |  | | --- | | Set-VBOHistorySettings -KeepAllSessions | |

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
