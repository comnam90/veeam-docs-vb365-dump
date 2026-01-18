---
title: "Get-VBOAzureVirtualNetwork"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboazurevirtualnetwork.html"
last_updated: "12/22/2025"
product_version: "8.3.0.2201"
---

# Get-VBOAzureVirtualNetwork


Short Description

Returns a network to which the Azure archiver appliance will be connected.

Syntax

|  |
| --- |
| Get-VBOAzureVirtualNetwork -ResourceGroup <VBOAzureResourceGroup> [-Name <String>] [-Location <VBOAzureLocation>] [<CommonParameters>] |

Detailed Description

This cmdlet returns the [VBOAzureVirtualNetwork](vboazurevirtualnetwork.md) object.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| ResourceGroup | Specifies a resource group that will be associated with the Azure archiver appliance. | Accepts the [VBOAzureResourceGroup](vboazureresourcegroup.md) object.  To get this object, run the [Get-VBOAzureResourceGroup](get-vboazureresourcegroup.md) cmdlet. | True | Named | False |
| Name | Specifies a name of the virtual network. The cmdlet will return the virtual network with this name. | String | False | Named | False |
| Location | Specifies a Microsoft Entra region. | Accepts the [VBOAzureLocation](vboazurelocation.md) object.  To get this object, run the [Get-VBOAzureLocation](get-vboazurelocation.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAzureVirtualNetwork](vboazurevirtualnetwork.md) object.

Example

Getting Virtual Network by Name

This example shows how to get a virtual network with the specified name.

|  |
| --- |
| $azureacc = Get-VBOAzureServiceAccount -Id f8e5ac3d-d883-4dd8-8de3-a8f315fb6ae2  $subscription = Get-VBOAzureSubscription -ServiceAccount $azureacc -Id "06b7354e-518f-4a10-b4c1-98f49d743012"  $rgroup = Get-VBOAzureResourceGroup -Subscription $subscription -Name "ResourceGroupName"  Get-VBOAzureVirtualNetwork -ResourceGroup $rgroup -Name "VirtualNetworkName" |

Perform the following steps:

1. Run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $azureacc variable.
2. Run the [Get-VBOAzureSubscription](get-vboazuresubscription.md) cmdlet. Set the $azureacc variable as the ServiceAccount parameter value. Specify the Id parameter value. Save the result to the $subscription variable.
3. Run the [Get-VBOAzureResourceGroup](get-vboazureresourcegroup.md) cmdlet. Specify the $subscription variable as the Subscription parameter value. Specify the Name parameter value. Save the result to the $rgroup variable.
4. Run the Get-VBOAzureVirtualNetwork cmdlet. Specify the $rgroup variable as the ResourceGroup parameter value. Specify the Name parameter value.

Related Commands

* [Get-VBOAzureResourceGroup](get-vboazureresourcegroup.md)
* [Get-VBOAzureLocation](get-vboazurelocation.md)
* [Get-VBOAzureSubscription](get-vboazuresubscription.md)
* [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md)


