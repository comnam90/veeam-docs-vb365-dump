---
title: "get-vborestoresession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vborestoresession.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns Veeam Backup for Microsoft 365 restore sessions.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get a restore session with a specified name, status or result.

|  |
| --- |
| Get-VBORestoreSession [-Name <String>] [-Status <VBORestoreSessionStatus>] [-Result <VBORestoreSessionResult>] [-Last] [<CommonParameters>] |

* Get a restore session with a specified ID.

|  |
| --- |
| Get-VBORestoreSession -Id <Guid> [<CommonParameters>] |

Detailed Description

This cmdlet returns restore sessions.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Name | Specifies a name of the restore session. The cmdlet will return the restore session with this name. | String | False | Named | False |
| Status | Specifies the current status of the restore session:   * Running * Stopped   The cmdlet will return the restore session with the specified status. | VBORestoreSessionStatus | False | Named | False |
| Result | Specifies the status of the completed restore session:   * Success * Warning * Failed   The cmdlet will return the restore session with the specified result. | VBORestoreSessionResult | False | Named | False |
| Last | Defines that the cmdlet will return the latest restore session.  Default: False | SwitchParameter | False | Named | False |
| Id | Specifies an ID of the restore session. The cmdlet will return details of the restore session with this ID. | Guid | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1. Getting Specific Restore Session by ID

|  |  |
| --- | --- |
| This command returns a restore session with the ID 4a4aaaa4-4aa4-44a4-aaa4-a4a444444aa4.  |  | | --- | | Get-VBORestoreSession -Id 4a4aaaa4-4aa4-44a4-aaa4-a4a444444aa4 | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2. Getting Specific Restore Session by Name

|  |  |
| --- | --- |
| This command returns a restore session with the specified name.  |  | | --- | | Get-VBORestoreSession -Name "TestRestoreSession" | |

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
