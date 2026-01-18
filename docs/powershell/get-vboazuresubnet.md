---
title: "Get-VBOAzureSubNet"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboazuresubnet.html"
last_updated: "12/19/2025"
product_version: "8.3.0.2201"
---

# Get-VBOAzureSubNet


Short Description

Returns the Azure archiver appliance subnet.

Syntax

|  |
| --- |
| Get-VBOAzureSubNet -VirtualNetwork <VBOAzureVirtualNetwork> [-Name <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns the [VBOAzureSubNet](vboazuresubnet.md) object.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| VirtualNetwork | Specifies a network to which the Azure archiver appliance will be connected. | Accepts the [VBOAzureVirtualNetwork](vboazurevirtualnetwork.md) object.  To get this object, run the [Get-VBOAzureVirtualNetwork](get-vboazurevirtualnetwork.md) cmdlet. | True | Named | False |
| Name | Specifies a name of the subnet. The cmdlet will return the subnet with this name. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAzureSubNet](vboazuresubnet.md) object.

Example

Getting Azure Archiver Appliance Subnet

This example shows how to get the Azure archiver appliance subnet.

|  |
| --- |
| $azureacc = Get-VBOAzureServiceAccount -Id f8e5ac3d-d883-4dd8-8de3-a8f315fb6ae2  $subscription = Get-VBOAzureSubscription -ServiceAccount $azureacc -Id "06b7354e-518f-4a10-b4c1-98f49d743012"  $rgroup = Get-VBOAzureResourceGroup -Subscription $subscription -Name "ResourceGroupName"  $VN = Get-VBOAzureVirtualNetwork -ResourceGroup $rgroup -Name "VirtualNetworkName"  Get-VBOAzureSubNet -VirtualNetwork $VN -Name "SubnetName" |

Perform the following steps:

1. Run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $azureacc variable.
2. Run the [Get-VBOAzureSubscription](get-vboazuresubscription.md) cmdlet. Set the $azureacc variable as the ServiceAccount parameter value. Specify the Id parameter value. Save the result to the $subscription variable.
3. Run the [Get-VBOAzureResourceGroup](get-vboazureresourcegroup.md) cmdlet. Specify the $subscription variable as the Subscription parameter value. Specify the Name parameter value. Save the result to the $rgroup variable.
4. Run the [Get-VBOAzureVirtualNetwork](get-vboazurevirtualnetwork.md) cmdlet. Specify the $rgroup variable as the ResourceGroup parameter value. Specify the Name parameter value. Sane the result to the $VN variable.
5. Run the Get-VBOAzureSubNet cmdlet. Specify the $VN variable as the VirtualNetwork parameter value. Specify the Name parameter value.

Related Commands

* [Get-VBOAzureVirtualNetwork](get-vboazurevirtualnetwork.md)

* [Get-VBOAzureResourceGroup](get-vboazureresourcegroup.md)
* [Get-VBOAzureSubscription](get-vboazuresubscription.md)
* [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md)


