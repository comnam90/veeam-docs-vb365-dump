---
title: "stop-vborepositoryupgradesession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/stop-vborepositoryupgradesession.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Stops sessions started to upgrade backup repositories.

Syntax

|  |
| --- |
| Stop-VBORepositoryUpgradeSession -Session <VBORepositoryUpgradeSession> [<CommonParameters>] |

Detailed Description

This cmdlet stops sessions that are started to upgrade backup repositories.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Session | Specifies a session that is started to upgrade backup repositories. The cmdlet will stop this session. | Accepts the VBORepositoryUpgradeSession object.  To get this object, run the [Get-VBORepositoryUpgradeSession](get-vborepositoryupgradesession.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Stopping Upgrade Sessions

This command stops sessions started to upgrade backup repositories.

|  |
| --- |
| Get-VBORepositoryUpgradeSession | foreach{Stop-VBORepositoryUpgradeSession -Session $\_} |

Related Commands

[Get-VBORepositoryUpgradeSession](get-vborepositoryupgradesession.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
