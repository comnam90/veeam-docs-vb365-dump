---
title: "start-vborepositoryindexingsession"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/start-vborepositoryindexingsession.html"
last_updated: "4/16/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Creates and starts an indexing session when a backup proxy server collects and sends the restore points metadata of a backup repository associated with this backup proxy server to the Veeam Backup for Microsoft 365 controller.

Syntax

|  |
| --- |
| Start-VBORepositoryIndexingSession -Repository <VBORepository> [-Force] [<CommonParameters>] |

Detailed Description

This cmdlet creates and starts an indexing session when a backup proxy server collects and sends the restore points metadata of a backup repository associated with this backup proxy server to the Veeam Backup for Microsoft 365 controller. This information is accumulated in the Veeam Backup for Microsoft 365 configuration database created on the PostgreSQL instance. By default, indexing is performed automatically after you re-attach a backup repository to the same or another Veeam Backup for Microsoft 365 server or after upgrading Veeam Backup for Microsoft 365 to a newer version.

Veeam Backup for Microsoft 365 put a backup repository into the Unindexed state until indexing finishes.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Repository | Specifies a backup repository. The cmdlet will create an indexing session for this backup repository. | Accepts the VBORepository object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | False |
| Force | Defines that the cmdlet will start a session without showing warnings in the PowerShell console.  If you do not provide the parameter, the cmdlet will prompt you to confirm the operation.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBORepositoryIndexingSession object that contains details on the backup repository indexing.

Example

Starting Backup Repository Indexing Session

This example shows how to start an indexing session for the Azure Backup object storage repository.

|  |
| --- |
| $repository = Get-VBORepository -Name "Azure Backup"  Start-VBORepositoryIndexingSession -Repository $repository |

Perform the following steps:

1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable.
2. Run the Start-VBORepositoryIndexingSession cmdlet. Set the $repository variable as the Repository parameter value.

Related Commands

[Get-VBORepository](get-vborepository.md)

Page updated 4/16/2025

Page content applies to build 8.3.0.2201
