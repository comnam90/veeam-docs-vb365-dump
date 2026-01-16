---
title: "disable-vbocopyjob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/disable-vbocopyjob.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Temporarily disables a backup copy job.

Syntax

|  |
| --- |
| Disable-VBOCopyJob -Job <VBOCopyJob> [<CommonParameters>] |

Detailed Description

This cmdlet temporarily disables the specified backup copy job. The backup copy job and its settings will remain in Veeam Backup for Microsoft 365. You can enable the job at any time by running the [Enable-VBOCopyJob](enable-vbocopyjob.md) cmdlet.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup copy job that you want to disable. | Accepts the VBOCopyJob object.  To get this object, run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet. | True | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Disabling Backup Copy Job

This example shows how to disable a backup copy job.

|  |
| --- |
| $copyjob = Get-VBOCopyJob -Id 8b6b539e-15cc-4ed6-bd1d-b8c7c918f413  Disable-VBOCopyJob -Job $copyjob |

Perform the following steps:

1. Run the [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet. Specify the Id parameter value. Save the result to the $copyjob variable.
2. Run the Disable-VBOCopyJob cmdlet. Set the $copyjob variable as the Job parameter value.

Related Commands

* [Get-VBOCopyJob](get-vbocopyjob.md)
* [Enable-VBOCopyJob](enable-vbocopyjob.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
