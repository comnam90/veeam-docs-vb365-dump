---
title: "start-vborepositoryupgradesession"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/start-vborepositoryupgradesession.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Creates and starts a session to upgrade backup repositories.

Syntax

|  |
| --- |
| Start-VBORepositoryUpgradeSession -Repository <VBORepository> [<CommonParameters>] |

Detailed Description

This cmdlet creates and starts a session to upgrade a backup repository. You may need this if you have upgraded Veeam Backup for Microsoft 365 to a new version and all backup repositories configured in your environment are marked as Out of Date.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Repository | Specifies a backup repository. The cmdlet will upgrade this backup repository. | Accepts the VBORepository object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBORepositoryUpgradeSession object that contains details on sessions that are running to upgrade backup repositories.

Example

Upgrading Backup Repository

This example shows how to upgrade a backup repository.

|  |
| --- |
| $repository = Get-VBORepository -Name "Repository 05"  Start-VBORepositoryUpgradeSession -Repository $repository |

Perform the following steps:

1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable.
2. Run the Start-VBORepositoryUpgradeSession cmdlet. Set the $repository variable as the Repository parameter value.

Related Commands

[Get-VBORepository](get-vborepository.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
