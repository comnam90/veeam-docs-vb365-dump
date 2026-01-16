---
title: "enable-vbojob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/enable-vbojob.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Enables a backup job.

Syntax

|  |
| --- |
| Enable-VBOJob -Job <VBOJob> [<CommonParameters>] |

Detailed Description

This cmdlet enables a disabled backup job. When you disable a job, you put it on hold until you enable it with this cmdlet.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup job that you want to enable. | Accepts the VBOJob object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Enabling Backup Job

This example shows how to enable the temporarily disabled backup job.

|  |
| --- |
| $job = Get-VBOJob -Name "ABC Backup"  Enable-VBOJob -Job $job |

Perform the following steps:

1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get the backup job that you want to enable. Save the result to the $job variable.
2. Run the Enable-VBOJob cmdlet with the $job variable.

Related Commands

[Get-VBOJob](get-vbojob.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
