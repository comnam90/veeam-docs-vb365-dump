---
title: "Get-VBORepositoryOwnerChangeSession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vborepositoryownerchangesession.html"
last_updated: "1/13/2026"
product_version: "8.3.0.2201"
---

# Get-VBORepositoryOwnerChangeSession


Short Description

Returns a change owner session started to move a backup repository to another backup proxy server or backup proxy pool.

Syntax

|  |
| --- |
| Get-VBORepositoryOwnerChangeSession -SessionId <Guid> [<CommonParameters>] |

Detailed Description

This cmdlet returns a session when Veeam Backup for Microsoft 365 moves a backup repository to another backup proxy server or backup proxy pool.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| SessionId | Specifies an ID of the session that is started to move a backup repository to another backup proxy server or backup proxy pool. The cmdlet will return details of this session. | Guid | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBORepositoriesOwnerChangeSession](vborepositoriesownerchangesession.md) object that contains details on a session when Veeam Backup for Microsoft 365 moves a backup repository to another backup proxy server or backup proxy pool.

Example

Getting Change Owner Session by Session ID

This command returns a change owner session with the ID d96f55a4-d15d-0000-b0f0-d51d17ccdab6.

|  |
| --- |
| Get-VBORepositoryOwnerChangeSession -SessionId d96f55a4-d15d-0000-b0f0-d51d17ccdab6 |


