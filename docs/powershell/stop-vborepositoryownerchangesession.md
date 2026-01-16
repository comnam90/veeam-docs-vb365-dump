---
title: "stop-vborepositoryownerchangesession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/stop-vborepositoryownerchangesession.html"
last_updated: "5/27/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Stops change owner sessions.

Syntax

|  |
| --- |
| Stop-VBORepositoryOwnerChangeSession -SessionId <Guid> [<CommonParameters>] |

Detailed Description

This cmdlet stops a session when Veeam Backup for Microsoft 365 moves a backup repository to another backup proxy server or backup proxy pool.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| SessionId | Specifies an ID of the session that is started to move a backup repository to another backup proxy server or backup proxy pool. The cmdlet will stop this session. | Guid | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Stopping Change Owner Session

This command stops a change owner session with the ID d96f55a4-d15d-0000-b0f0-d51d17ccdab6.

|  |
| --- |
| Stop-VBORepositoryOwnerChangeSession -SessionId d96f55a4-d15d-0000-b0f0-d51d17ccdab6 |

Page updated 5/27/2025

Page content applies to build 8.3.0.2201
