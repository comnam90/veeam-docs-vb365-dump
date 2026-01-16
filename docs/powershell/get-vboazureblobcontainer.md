---
title: "get-vboazureblobcontainer"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboazureblobcontainer.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns Microsoft Azure Blob containers.

Syntax

|  |
| --- |
| Get-VBOAzureBlobContainer -ConnectionSettings <VBOAzureBlobConnectionSettings> [-Name <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of Microsoft Azure Blob containers.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| ConnectionSettings | Specifies an active session with Microsoft Azure Blob Storage. The cmdlet will return an array of the containers added to this object storage repository. | Accepts the VBOAzureBlobConnectionSettings object.  To create this object, run the [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md) cmdlet. | True | Named | False |
| Name | Specifies a name of the Microsoft Azure Blob container that you want to get. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAzureBlobContainer object that returns an array of Microsoft Azure Blob containers.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Microsoft Azure Blob Containers

|  |  |
| --- | --- |
| This example shows how to get all containers added to Microsoft Azure Blob Storage.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Id 133dae61-cfce-4fe0-8f8d-cbe52bd5612a  $connection = New-VBOAzureBlobConnectionSettings -Account $account -RegionType Global  Get-VBOAzureBlobContainer -ConnectionSettings $connection |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable. 3. Run the Get-VBOAzureBlobContainer cmdlet. Set the $connection variable as the ConnectionSettings parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Specific Microsoft Azure Blob Container

|  |  |
| --- | --- |
| This example shows how to get the Container 05 container added to Microsoft Azure Blob Storage.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Id 133dae61-cfce-4fe0-8f8d-cbe52bd5612a  $connection = New-VBOAzureBlobConnectionSettings -Account $account -RegionType Global  Get-VBOAzureBlobContainer -ConnectionSettings $connection -Name "Container 05" |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable. 3. Run the Get-VBOAzureBlobContainer cmdlet. Set the $connection variable as the ConnectionSettings parameter value. Specify the Name parameter value. |

Related Commands

* [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md)
* [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
