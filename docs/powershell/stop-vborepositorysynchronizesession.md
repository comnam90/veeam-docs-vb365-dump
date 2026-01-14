---
title: "stop-vborepositorysynchronizesession"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/stop-vborepositorysynchronizesession.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Stops sessions that are running to synchronize cache between object storage repositories and the PersistentCache database on the PostgreSQL instance.

Syntax

|  |
| --- |
| Stop-VBORepositorySynchronizeSession -Session <VBORepositorySynchronizeSession> [<CommonParameters>] |

Detailed Description

This cmdlet stops sessions that are running to synchronize cache between object storage repositories and the PersistentCache database on the PostgreSQL instance.

|  |
| --- |
| ![Stop-VBORepositorySynchronizeSession](images/icon_note.webp) Note |
| If you stop the synchronization session and then start it again, the synchronization process will start from the moment where it has been stopped. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Session | Specifies a synchronization session. The cmdlet will stop this session. | Accepts the VBORepositorySynchronizeSession object.  To get this object, run the [Get-VBORepositorySynchronizeSession](get-vborepositorysynchronizesession.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBORepositorySynchronizeSession object that contains details on the synchronization status of an object storage repository.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Stopping All Synchronization Sessions

|  |  |
| --- | --- |
| This command stops all sessions that are running to synchronize cache between object storage repositories and the PersistentCache database on the PostgreSQL instance.  |  | | --- | | Get-VBORepositorySynchronizeSession | foreach{Stop-VBORepositorySynchronizeSession -Session $\_} | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Stopping Specific Synchronization Session

|  |  |
| --- | --- |
| This example shows how to stop a session that is running to synchronize cache between the Azure object storage repository and the PersistentCache database on the PostgreSQL instance.  |  | | --- | | $azurestorage = Get-VBORepository -Name "Azure"  $session = Get-VBORepositorySynchronizeSession -Repository $azurestorage  Stop-VBORepositorySynchronizeSession -Session $session |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $azurestorage variable. 2. Run the [Get-VBORepositorySynchronizeSession](get-vborepositorysynchronizesession.md) cmdlet. Set the $azurestorage variable as the Repository parameter value. Save the result to the $session variable.   The cmdlet output will contain the following details on synchronization status of an object storage repository: RepositoryId, RepositoryName and Status.   1. Run the Stop-VBORepositorySynchronizeSession cmdlet. Set the $session variable as the Session parameter value. |

Related Commands

* [Get-VBORepository](get-vborepository.md)
* [Get-VBORepositorySynchronizeSession](get-vborepositorysynchronizesession.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
