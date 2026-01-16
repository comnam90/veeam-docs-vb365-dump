---
title: "get-vboazureblobfolder"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboazureblobfolder.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns Microsoft Azure Blob folders.

Syntax

|  |
| --- |
| Get-VBOAzureBlobFolder -Container <VBOAzureBlobContainer> [-Name <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of Microsoft Azure Blob folders from the specified container.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Container | Specifies a Microsoft Azure Blob container. The cmdlet will return folders from this container. | Accepts the VBOAzureBlobContainer object.  To get this object, run the [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md) cmdlet. | True | Named | False |
| Name | Specifies a name of the Microsoft Azure Blob folder that you want to get. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAzureBlobFolder object that contains an array of Microsoft Azure Blob folders.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Microsoft Azure Blob Folders

|  |  |
| --- | --- |
| This example shows how to get all folders from the Microsoft Azure Blob Storage container.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Id 133dae61-cfce-4fe0-8f8d-cbe52bd5612a  $connection = New-VBOAzureBlobConnectionSettings -Account $account -RegionType Global  $container = Get-VBOAzureBlobContainer -ConnectionSettings $connection  Get-VBOAzureBlobFolder -Container $container |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable. 3. Run the [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md) cmdlet. Set the $connection variable as the ConnectionSettings parameter value. Save the result to the $container variable. 4. Run the Get-VBOAzureBlobFolder cmdlet. Set the $container variable as the Container parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Microsoft Azure Blob Folder with Specific Name

|  |  |
| --- | --- |
| This example shows how to get the Folder06 folder from the Microsoft Azure Blob Storage container.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Id 133dae61-cfce-4fe0-8f8d-cbe52bd5612a  $connection = New-VBOAzureBlobConnectionSettings -Account $account -RegionType Global  $container = Get-VBOAzureBlobContainer -ConnectionSettings $connection  Get-VBOAzureBlobFolder -Container $container -Name "Folder06" |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable. 3. Run the [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md) cmdlet. Set the $connection variable as the ConnectionSettings parameter value. Save the result to the $container variable. 4. Run the Get-VBOAzureBlobFolder cmdlet. Set the $container variable as the Container parameter value. Specify the Name parameter value. |

Related Commands

* [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md)
* [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md)
* [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
