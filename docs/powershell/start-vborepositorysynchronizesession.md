---
title: "Start-VBORepositorySynchronizeSession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/start-vborepositorysynchronizesession.html"
last_updated: "1/29/2026"
product_version: "8.3.0.2201"
---

# Start-VBORepositorySynchronizeSession


Short Description

Creates and starts a session to synchronize cache between object storage repositories and the PersistentCache database on the PostgreSQL instance.

Syntax

|  |
| --- |
| Start-VBORepositorySynchronizeSession -Repository <VBORepository> [<CommonParameters>] |

Detailed Description

This cmdlet creates and starts a session to synchronize cache between object storage repositories and the PersistentCache database on the PostgreSQL instance.

For more information on cache synchronization, see the [Synchronizing Cache](https://helpcenter.veeam.com/docs/vbo365/guide/synch_repositories.html?ver=80) section of the Veeam Backup for Microsoft 365 User Guide.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Repository | Specifies an object storage repository. The cmdlet will synchronize cache between this object storage repository and the PersistentCache database on the PostgreSQL instance. | Accepts the [VBORepository](vborepository.md) object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBORepositorySynchronizeSession](vborepositorysynchronizesession.md) object that contains details on the synchronization status of an object storage repository.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Synchronizing Microsoft Azure Blob Storage Cache

|  |  |
| --- | --- |
| This example shows how to start synchronizing Microsoft Azure Blob Storage cache with the PersistentCache database on the PostgreSQL instance.  |  | | --- | | $azurestorage = Get-VBORepository -Name "Azure"  Start-VBORepositorySynchronizeSession -Repository $azurestorage  RepositoryId                            RepositoryName                          Status  ------------                            --------------                          ------  1e74b71a-def4-41c6-8826-5d6fc8ad7c0f    Azure                                   Synchronizing... (35%) |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $azurestorage variable. 2. Run the Start-VBORepositorySynchronizeSession cmdlet. Set the $azurestorage variable as the Repository parameter value.   The cmdlet output will contain the following details on synchronization status of an object storage repository: RepositoryId, RepositoryName and Status. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Synchronizing Amazon S3 Object Storage

|  |  |
| --- | --- |
| This example shows how to start synchronizing Amazon S3 object storage repository cache with the PersistentCache database on the PostgreSQL instance.  |  | | --- | | $amazonstorage = Get-VBORepository -Name "Amazon S3"  Start-VBORepositorySynchronizeSession -Repository $amazonstorage  RepositoryId                            RepositoryName                          Status  ------------                            --------------                          ------  d745ba88-719d-4bc6-883a-5559e001ac62    Amazon S3                               Synchronizing... (68%) |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $amazonstorage variable. 2. Run the Start-VBORepositorySynchronizeSession cmdlet. Set the $amazonstorage variable as the Repository parameter value.   The cmdlet output will contain the following details on synchronization status of an object storage repository: RepositoryId, RepositoryName and Status. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Synchronizing S3 Compatible Object Storage

|  |  |
| --- | --- |
| This example shows how to start synchronizing S3 Compatible object storage repository cache with the PersistentCache database on the PostgreSQL instance.  |  | | --- | | $s3compatible = Get-VBORepository -Name "S3 Compatible object storage"  Start-VBORepositorySynchronizeSession -Repository $s3compatible  RepositoryId                            RepositoryName                          Status  ------------                            --------------                          ------  af061087-7b8b-4c76-84b7-8a2858b15ae6    S3 Compatible object storage            Synchronizing... (51%) |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $s3compatible variable. 2. Run the Start-VBORepositorySynchronizeSession cmdlet. Set the $s3compatible variable as the Repository parameter value.   The cmdlet output will contain the following details on synchronization status of an object storage repository: RepositoryId, RepositoryName and Status. |

Related Commands

[Get-VBORepository](get-vborepository.md)


