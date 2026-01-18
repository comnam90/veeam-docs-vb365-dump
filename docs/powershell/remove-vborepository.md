---
title: "Remove-VBORepository"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vborepository.html"
last_updated: "12/8/2025"
product_version: "8.3.0.2201"
---

# Remove-VBORepository


Short Description

Removes backup repositories.

Syntax

|  |
| --- |
| Remove-VBORepository -Repository <VBORepository> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet allows you to remove backup repositories from the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| ![Remove-VBORepository](images/icon_note.webp) Note |
| Before removing backup repositories make sure that there are no backup jobs targeted at this repository. Otherwise Veeam Backup for Microsoft 365 will not allow you to remove this repository. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Repository | Specifies a backup repository. The cmdlet will remove this backup repository from the Veeam Backup for Microsoft 365 infrastructure. | Accepts the [VBORepository](vborepository.md) object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | True (ByValue) |
| Force | Defines that the cmdlet will also remove object storage if it was linked to this JET-based backup repository.  Default: False | SwitchParameter | False | Named | False |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing Backup Repository

This example shows how to remove the Repository 05 backup repository from the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| $repository = Get-VBORepository -Name "Repository 05"  Remove-VBORepository -Repository $repository |

Perform the following steps:

1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable.
2. Run the Remove-VBORepository cmdlet. Set the $repository variable as the Repository parameter value.

Related Commands

[Get-VBORepository](get-vborepository.md)


