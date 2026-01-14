---
title: "get-vboazureresourcegroup"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboazureresourcegroup.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns a resource group that will be associated with the Azure archiver appliance.

Syntax

|  |
| --- |
| Get-VBOAzureResourceGroup -Subscription <VBOAzureSubscription> [-Location <VBOAzureLocation>] [-Name <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns the VBOAzureResourceGroup object.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Subscription | Specifies a subscription associated with a user account that will be used to access Azure Blob Storage. | Accepts the VBOAzureSubscription object.  To get this object, run the [Get-VBOAzureSubscription](get-vboazuresubscription.md) cmdlet. | True | Named | True (ByValue) |
| Location | Specifies a Microsoft Entra region. | Accepts the VBOAzureLocation object.  To get this object, run the [Get-VBOAzureLocation](get-vboazurelocation.md) cmdlet. | False | Named | False |
| Name | Specifies a name of the resource group. The cmdlet will return the resource group with this name. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAzureResourceGroup object that will be associated with the Azure archiver appliance.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Resource Groups in Azure Location

|  |  |
| --- | --- |
| This example shows how to get all resource groups in the specified Microsoft Entra region.  |  | | --- | | $azureacc = Get-VBOAzureServiceAccount -Id f8e5ac3d-d883-4dd8-8de3-a8f315fb6ae2  $subscription = Get-VBOAzureSubscription -ServiceAccount $azureacc -Id "06b7354e-518f-4a10-b4c1-98f49d743012"  $location = Get-VBOAzureLocation -Subscription $subscription -Name westeurope  Get-VBOAzureResourceGroup -Subscription $subscription -Location $location |  Perform the following steps:   1. Run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $azureacc variable. 2. Run the [Get-VBOAzureSubscription](get-vboazuresubscription.md) cmdlet. Set the $azureacc variable as the ServiceAccount parameter value. Specify the Id parameter value. Save the result to the $subscription variable. 3. Run the [Get-VBOAzureLocation](get-vboazurelocation.md) cmdlet. Specify the $subscription variable as the Subscription parameter value. Specify the Name parameter value. Save the result to the $location variable. 4. Run the Get-VBOAzureResourceGroup cmdlet. Specify the $subscription variable as the Subscription parameter value and the $location as the Location parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Resource Group by Name

|  |  |
| --- | --- |
| This example shows how to get a resource group with the specified name.  |  | | --- | | $azureacc = Get-VBOAzureServiceAccount -Id f8e5ac3d-d883-4dd8-8de3-a8f315fb6ae2  $subscription = Get-VBOAzureSubscription -ServiceAccount $azureacc -Id "06b7354e-518f-4a10-b4c1-98f49d743012"  Get-VBOAzureResourceGroup -Subscription $subscription -Name "ResourceGroupName" |  Perform the following steps:   1. Run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $azureacc variable. 2. Run the [Get-VBOAzureSubscription](get-vboazuresubscription.md) cmdlet. Set the $azureacc variable as the ServiceAccount parameter value. Specify the Id parameter value. Save the result to the $subscription variable. 3. Run the Get-VBOAzureResourceGroup cmdlet. Specify the $subscription variable as the Subscription parameter value. Specify the Name parameter value. |

Related Commands

* [Get-VBOAzureSubscription](get-vboazuresubscription.md)
* [Get-VBOAzureLocation](get-vboazurelocation.md)
* [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
