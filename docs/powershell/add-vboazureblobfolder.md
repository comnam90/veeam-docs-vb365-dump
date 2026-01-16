---
title: "add-vboazureblobfolder"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboazureblobfolder.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Creates Microsoft Azure Blob folders.

Syntax

|  |
| --- |
| Add-VBOAzureBlobFolder -Container <VBOAzureBlobContainer> -Name <String> [<CommonParameters>] |

Detailed Description

This cmdlet creates Microsoft Azure Blob folders.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Container | Specifies the Microsoft Azure Blob container. The cmdlet will create a folder in this container. | Accepts the VBOAzureBlobContainer object.  To get this object, run the [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md) cmdlet. | True | Named | False |
| Name | Specifies a name of the Microsoft Azure Blob folder. The cmdlet will create the Microsoft Azure Blob folder with this name. | String | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAzureBlobFolder object that contains an array of Microsoft Azure Blob folders.

Example

Creating Microsoft Azure Blob Folder

This example shows how to create a Microsoft Azure Blob folder.

|  |
| --- |
| $account = Get-VBOAzureBlobAccount -Id 133dae61-cfce-4fe0-8f8d-cbe52bd5612a  $connection = New-VBOAzureBlobConnectionSettings -Account $account -RegionType Global  $container = Get-VBOAzureBlobContainer -ConnectionSettings $connection  Add-VBOAzureBlobFolder -Container $container -Name "Images" |

Perform the following steps:

1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable.
2. Run the [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value.
3. Run the [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md) cmdlet. Set the $connection variable as the ConnectionSettings parameter value.
4. Run the Add-VBOAzureBlobFolder cmdlet. Set the $container variable as the Container parameter value. Specify the Name parameter value.

Related Commands

* [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md)
* [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md)
* [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
