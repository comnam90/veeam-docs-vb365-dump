---
title: "New-VBOAzureBlobConnectionSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vboazureblobconnectionsettings.html"
last_updated: "12/22/2025"
product_version: "8.3.0.2201"
---

# New-VBOAzureBlobConnectionSettings


Short Description

Defines connection settings to Microsoft Azure Blob Storage.

Syntax

|  |
| --- |
| New-VBOAzureBlobConnectionSettings -Account <VBOAzureBlobAccount> -RegionType <VBOAzureRegionType> [<CommonParameters>] |

Detailed Description

This cmdlet creates the [VBOAzureBlobConnectionSettings](vboazureblobconnectionsettings.md) object. This object contains connection settings to Microsoft Azure Blob Storage.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Account | Specifies Microsoft Azure Blob Storage account credentials. The cmdlet will use this storage account credentials to connect to Microsoft Azure Blob Storage. | Accepts the [VBOAzureBlobAccount](vboazureblobaccount.md) object.  To get this object, run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. | True | Named | False |
| RegionType | Specifies the region type for Microsoft Azure Blob Storage. The cmdlet will connect to the selected region type and will set up a connection with Microsoft Azure Blob Storage. You can select the following types of region:   * Global * Germany * China * Government | VBOAzureRegionType | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAzureBlobConnectionSettings](vboazureblobconnectionsettings.md) object that defines connection settings to Microsoft Azure Blob Storage.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Connecting to Microsoft Azure Blob Storage of Global Region Type

|  |  |
| --- | --- |
| This example shows how to connect to Microsoft Azure Blob Storage of the Global region type.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Id 133dae61-cfce-4fe0-8f8d-cbe52bd5612a  New-VBOAzureBlobConnectionSettings -Account $account[0] -RegionType Global |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the New-VBOAzureBlobConnectionSettings cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Connecting to Microsoft Azure Blob Storage of Germany Region Type

|  |  |
| --- | --- |
| This example shows how to connect to Microsoft Azure Blob Storage of the Germany region type.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Id f4259b29-8cd3-48e9-8007-ad0faa26c474  New-VBOAzureBlobConnectionSettings -Account $account -RegionType Germany |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the New-VBOAzureBlobConnectionSettings cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Connecting to Microsoft Azure Blob Storage of China Region Type

|  |  |
| --- | --- |
| This example shows how to connect to Microsoft Azure Blob Storage of the China region type.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Id fbc5e563-7a1a-47bb-8ba5-eaae0f652a5f  New-VBOAzureBlobConnectionSettings -Account $account -RegionType China |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the New-VBOAzureBlobConnectionSettings cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Connecting to Microsoft Azure Blob Storage of Government Region Type

|  |  |
| --- | --- |
| This example shows how to connect to Microsoft Azure Blob Storage of the Government region type.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Id 936edf7c-7cf3-4ddc-9895-c7485ef4bb2c  New-VBOAzureBlobConnectionSettings -Account $account -RegionType Government |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the New-VBOAzureBlobConnectionSettings cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. |

Related Commands

[Get-VBOAzureBlobAccount](get-vboazureblobaccount.md)


