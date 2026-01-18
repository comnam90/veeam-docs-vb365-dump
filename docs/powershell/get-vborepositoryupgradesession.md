---
title: "Get-VBORepositoryUpgradeSession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vborepositoryupgradesession.html"
last_updated: "12/18/2025"
product_version: "8.3.0.2201"
---

# Get-VBORepositoryUpgradeSession


Short Description

Returns sessions started to upgrade backup repositories.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get all sessions started to upgrade backup repositories.

|  |
| --- |
| Get-VBORepositoryUpgradeSession [<CommonParameters>] |

* Get a session started to upgrade a specific backup repository.

|  |
| --- |
| Get-VBORepositoryUpgradeSession [-Repository <VBORepository>] [<CommonParameters>] |

Detailed Description

This cmdlet returns sessions that are started to upgrade backup repositories.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Repository | Specifies a backup repository. The cmdlet will return sessions that are started to upgrade the specified backup repository. | Accepts the [VBORepository](vborepository.md) object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBORepositoryUpgradeSession](vborepositoryupgradesession.md) object that contains details on sessions that are running to upgrade backup repositories.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Active Sessions Started to Upgrade Backup Repositories

|  |  |
| --- | --- |
| This command returns all active sessions that are started to upgrade backup repositories.  |  | | --- | | Get-VBORepositoryUpgradeSession | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Active Session Started to Upgrade Specific Backup Repository

|  |  |
| --- | --- |
| This example shows how to get an active session started to upgrade the Repository 09 backup repository.  |  | | --- | | $repository = Get-VBORepository -Name "Repository 09"  Get-VBORepositoryUpgradeSession -Repository $repository |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable. 2. Run the Get-VBORepositoryUpgradeSession cmdlet. Set the $repository variable as the Repository parameter value. |

Related Commands

[Get-VBORepository](get-vborepository.md)


