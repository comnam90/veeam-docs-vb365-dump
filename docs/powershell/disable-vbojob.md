---
title: "Disable-VBOJob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/disable-vbojob.html"
last_updated: "12/22/2025"
product_version: "8.3.0.2201"
---

# Disable-VBOJob


Short Description

Temporarily disables a backup job.

Syntax

|  |
| --- |
| Disable-VBOJob -Job <VBOJob> [<CommonParameters>] |

Detailed Description

This cmdlet temporarily disables the specified backup job. The backup job and its settings will remain in Veeam Backup for Microsoft 365. You can enable the job at any time by running the [Enable-VBOJob](enable-vbojob.md) cmdlet.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup job that you want to disable. | Accepts the [VBOJob](vbojob.md) object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Disabling Backup Job

This example shows how to disable a backup job.

|  |
| --- |
| $job = Get-VBOJob -Name "ABC Backup"  Disable-VBOJob -Job $job |

Perform the following steps:

1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to get the backup job that you want to disable. Save the result to the $job variable.
2. Run the Disable-VBOJob cmdlet with the $job variable.

Related Commands

* [Get-VBOJob](get-vbojob.md)
* [Enable-VBOJob](enable-vbojob.md)


