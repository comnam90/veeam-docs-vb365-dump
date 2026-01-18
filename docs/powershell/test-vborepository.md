---
title: "Test-VBORepository"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/test-vborepository.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Test-VBORepository


Short Description

Verifies the integrity of backed-up Exchange, SharePoint and Teams data in backup repositories.

Syntax

|  |
| --- |
| Test-VBORepository -Repository <VBORepository> [<CommonParameters>] |

Detailed Description

This cmdlet allows you to verify the integrity of Exchange, SharePoint and Teams data backups stored in backup repositories. The cmdlet returns objects stored in a specified backup repository that have certain inconsistencies in their backed-up data.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Repository | Specifies a backup repository.  The cmdlet will verify the integrity of Exchange, SharePoint and Teams data backups stored in this backup repository. | Accepts the [VBORepository](vborepository.md) object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns objects  stored in a specified backup repository that have certain inconsistencies in their backed-up data.

Example

Verifying Backup Repository Integrity

This example shows how to verify the integrity of the Repository 05 backup repository.

|  |
| --- |
| $repository = Get-VBORepository -Name "Repository 05"  Test-VBORepository -Repository $repository |

Perform the following steps:

1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable.
2. Run the Test-VBORepository cmdlet. Set the $repository variable as the Repository parameter value.

Related Commands

[Get-VBORepository](get-vborepository.md)


