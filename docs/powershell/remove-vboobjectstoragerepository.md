---
title: "remove-vboobjectstoragerepository"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vboobjectstoragerepository.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Removes an object storage repository from the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| ![Remove-VBOObjectStorageRepository](images/icon_note.webp) Note |
| In Veeam Backup for Microsoft 365 8, this cmdlet became deprecated. Use the [Remove-VBORepository](remove-vborepository.md) cmdlet with the Force:$true parameter instead. |

Syntax

|  |
| --- |
| Remove-VBOObjectStorageRepository -ObjectStorageRepository <VBOObjectStorageRepository> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes an object storage repository from the Veeam Backup for Microsoft 365 infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| ObjectStorageRepository | Specifies an object storage repository that you want to remove from the Veeam Backup for Microsoft 365 infrastructure. | Accepts the VBOObjectStorageRepository object.  To get this object, run the [Get-VBOObjectStorageRepository](get-vboobjectstoragerepository.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing Object Storage Repository

This example shows how to remove the Azure object storage repository from the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| $repository = Get-VBOObjectStorageRepository -Name "Azure"  Remove-VBOObjectStorageRepository -ObjectStorageRepository $repository |

Perform the following steps:

1. Run the [Get-VBOObjectStorageRepository](get-vboobjectstoragerepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable.
2. Run the Remove-VBOObjectStorageRepository cmdlet. Set the $repository variable as the ObjectStorageRepository parameter value.

Related Commands

[Get-VBOObjectStorageRepository](get-vboobjectstoragerepository.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
