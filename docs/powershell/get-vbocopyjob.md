---
title: "get-vbocopyjob"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbocopyjob.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns backup copy jobs.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get a backup copy job by the backup copy job ID.

|  |
| --- |
| Get-VBOCopyJob -Id <Guid> [<CommonParameters>] |

* Get backup copy job by the associated backup job or backup repository.

|  |
| --- |
| Get-VBOCopyJob [-BackupJob <VBOJob>] [-Repository <VBORepository>] [<CommonParameters>] |

Detailed Description

This cmdlet returns backup copy jobs configured in Veeam Backup for Microsoft 365. You can get all backup copy jobs or query a backup copy job by ID or associated backup job and backup repository.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Id | Specifies an ID of the backup copy job. The cmdlet will return the backup copy job with this ID. | Guid | True | Named | False |
| BackupJob | Specifies a backup job for which you have created a backup copy job. | Accepts the VBOJob object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | False | Named | False |
| Repository | Specifies an object storage repository. Veeam Backup for Microsoft 365 uses this object storage repository as a target for backup copy jobs. | Accepts the VBORepository object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOCopyJob object that contains settings for a backup copy job.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Backup Copy Job by ID

|  |  |
| --- | --- |
| This command returns a backup copy job by ID.  |  | | --- | | Get-VBOCopyJob -Id 8b6b539e-15cc-4ed6-bd1d-b8c7c918f413 | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Backup Copy Job by Backup Job

|  |  |
| --- | --- |
| This example shows how to get a backup copy job created for the backup job with the name ABC Backup.  |  | | --- | | $job = Get-VBOJob -Name "ABC Backup"  Get-VBOCopyJob -BackupJob $job |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Specify the Name parameter value. Save the result to the $job variable. 2. Run the Get-VBOCopyJob cmdlet. Set the $job variable as the BackupJob parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Backup Copy Job by Backup Repository

|  |  |
| --- | --- |
| This example shows how to get backup copy jobs that transfer backed-up data to the specified backup repository.  |  | | --- | | $repository = Get-VBORepository -Name "Azure Archive Storage"  Get-VBOCopyJob -Repository $repository |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable. 2. Run the Get-VBOCopyJob cmdlet. Set the $repository variable as the Repository parameter value. |

Related Commands

* [Get-VBOJob](get-vbojob.md)
* [Get-VBORepository](get-vborepository.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
