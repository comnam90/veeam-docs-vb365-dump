---
title: "Set-VBOServer"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboserver.html"
last_updated: "6/3/2025"
product_version: "8.3.0.2201"
---

# Set-VBOServer


Short Description

Allows you to specify temporary storage for export and save operations.

Syntax

|  |
| --- |
| Set-VBOServer [-TempFolderPath <String>] [<CommonParameters>] |

Detailed Description

This cmdlet allows you to specify temporary storage for export and save operations.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| TempFolderPath | Specifies a path to the folder that will be used as temporary storage for export and save operations.  Default: %temp% | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Defining Folder for Export and Save Operations

This command defines the folder where results of export and save operations will be saved.

|  |
| --- |
| Set-VBOServer -TempFolderPath "C:\TemporaryFolder" |


