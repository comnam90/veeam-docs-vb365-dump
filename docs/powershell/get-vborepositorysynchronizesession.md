---
title: "get-vborepositorysynchronizesession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vborepositorysynchronizesession.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns sessions that are running to synchronize cache between object storage repositories and the PersistentCache database on the PostgreSQL instance.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get all synchronization sessions.

|  |
| --- |
| Get-VBORepositorySynchronizeSession [<CommonParameters>] |

* Get synchronization sessions for a specific object storage repository.

|  |
| --- |
| Get-VBORepositorySynchronizeSession [-Repository <VBORepository>] [<CommonParameters>] |

Detailed Description

This cmdlet returns sessions that are running to synchronize cache between object storage repositories and the PersistentCache database on the PostgreSQL instance.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Repository | Specifies an object storage repository. The cmdlet will return details of metadata (cache) synchronization between this object storage repository and the PersistentCache database created for this object storage repository on the PostgreSQL instance. | Accepts the VBORepository object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBORepositorySynchronizeSession object that contains details on the synchronization of cache between an object storage repository and the PersistentCache database on the PostgreSQL instance.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Synchronization Sessions

|  |  |
| --- | --- |
| This command returns all sessions that are running to synchronize cache between object storage repositories and the PersistentCache database on the PostgreSQL instance.  |  | | --- | | Get-VBORepositorySynchronizeSession | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Synchronization Sessions of Specific Object Storage

|  |  |
| --- | --- |
| This example shows how to get sessions that are running to synchronize cache between the specific object storage repository and the PersistentCache database on the PostgreSQL instance.  |  | | --- | | $azurestorage = Get-VBORepository -Name "Azure"  Get-VBORepositorySynchronizeSession -Repository $azurestorage |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $azurestorage variable. 2. Run the Get-VBORepositorySynchronizeSession cmdlet. Set the $azurestorage variable as the Repository parameter value.   The cmdlet output will contain the following details on synchronization status of an object storage repository: RepositoryId, RepositoryName and Status. |

Related Commands

[Get-VBORepository](get-vborepository.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
