---
title: "get-vboazurevirtualmachinesize"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboazurevirtualmachinesize.html"
last_updated: "4/11/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns the Azure archiver appliance size.

Syntax

|  |
| --- |
| Get-VBOAzureVirtualMachineSize -Subscription <VBOAzureSubscription> -Location <VBOAzureLocation> [-Name <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns the VBOAzureVirtualMachineSize object. This object contains the size of an auxiliary virtual machine in Microsoft Azure that is deployed and configured automatically by Veeam Backup for Microsoft 365.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Subscription | Specifies a subscription associated with a user account that will be used to access Azure Blob Storage. | Accepts the VBOAzureSubscription object.  To get this object, run the [Get-VBOAzureSubscription](get-vboazuresubscription.md) cmdlet. | True | Named | False |
| Location | Specifies a Microsoft Entra region. | Accepts the VBOAzureLocation object.  To get this object, run the [Get-VBOAzureLocation](get-vboazurelocation.md) cmdlet. | True | Named | False |
| Name | Specifies a name of an auxiliary virtual machine. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAzureVirtualMachineSize object.

Example

Getting Azure Archiver Appliance Size

This example shows how to get the Azure archiver appliance size.

|  |
| --- |
| $azureacc = Get-VBOAzureServiceAccount -Id f8e5ac3d-d883-4dd8-8de3-a8f315fb6ae2  $subscription = Get-VBOAzureSubscription -ServiceAccount $azureacc -Id "06b7354e-518f-4a10-b4c1-98f49d743012"  $location = Get-VBOAzureLocation -Subscription $subscription -Name westeurope  Get-VBOAzureVirtualMachineSize -Subscription $subscription -Location $location -Name Standard\_F8s\_v2 |

Perform the following steps:

1. Run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $azureacc variable.
2. Run the [Get-VBOAzureSubscription](get-vboazuresubscription.md) cmdlet. Set the $azureacc variable as the ServiceAccount parameter value. Specify the Id parameter value. Save the result to the $subscription variable.
3. Run the [Get-VBOAzureLocation](get-vboazurelocation.md) cmdlet. Specify the $subscription variable as the Subscription parameter value. Specify the Name parameter value. Save the result to the $location variable.
4. Run the Get-VBOAzureVirtualMachineSize cmdlet. Specify the $subscription variable as the Subscription parameter value and the $location as the Location parameter value. Specify the Name parameter value.

Related Commands

* [Get-VBOAzureSubscription](get-vboazuresubscription.md)
* [Get-VBOAzureLocation](get-vboazurelocation.md)
* [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md)

Page updated 4/11/2025

Page content applies to build 8.3.0.2201
