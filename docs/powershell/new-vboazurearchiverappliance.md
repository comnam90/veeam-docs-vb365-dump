---
title: "New-VBOAzureArchiverAppliance"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vboazurearchiverappliance.html"
last_updated: "12/22/2025"
product_version: "8.3.0.2201"
---

# New-VBOAzureArchiverAppliance


Short Description

Defines the Azure archiver appliance settings.

Syntax

This cmdlet provides parameter sets that allow you to:

* Define the Azure archiver appliance settings by specifying a range of IPv4 addresses for a subnet.

|  |
| --- |
| New-VBOAzureArchiverAppliance [-VmSize <VBOAzureVirtualMachineSize>] [-RedirectorPort <Int32>] [-ResourceGroup <VBOAzureResourceGroup>] [-VirtualNetwork <VBOAzureVirtualNetwork>] [-Subnet <VBOAzureSubnet>] -IpRanges <String[]> [<CommonParameters>] |

* Define the Azure archiver appliance settings by specifying a public IPv4 address of a backup proxy server.

|  |
| --- |
| New-VBOAzureArchiverAppliance [-VmSize <VBOAzureVirtualMachineSize>] [-RedirectorPort <Int32>] [-ResourceGroup <VBOAzureResourceGroup>] [-VirtualNetwork <VBOAzureVirtualNetwork>] [-Subnet <VBOAzureSubnet>] -ProxyIpRange <VBOProxy> [<CommonParameters>] |

* Define the Azure archiver appliance settings by specifying public IPv4 addresses of all backup proxy servers added to a backup proxy pool.

|  |
| --- |
| New-VBOAzureArchiverAppliance [-VmSize <VBOAzureVirtualMachineSize>] [-RedirectorPort <Int32>] [-ResourceGroup <VBOAzureResourceGroup>] [-VirtualNetwork <VBOAzureVirtualNetwork>] [-Subnet <VBOAzureSubnet>] -ProxyPoolIpRange <VBOProxyPool> [<CommonParameters>] |

Detailed Description

This cmdlet creates the [VBOAzureArchiverAppliance](vboazurearchiverappliance.md) object. This object contains settings of the Azure archiver appliance that Veeam Backup for Microsoft 365 will use when transferring backed-up data between different instances of Azure Blob Storage or to Azure Blob Storage Archive.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| VmSize | Specifies a size of the Azure archiver appliance.  Default: Standard\_B4ms (4 CPU/16 GB) | Accepts the [VBOAzureVirtualMachineSize](vboazurevirtualmachinesize.md) object.  To get this object, run the [Get-VBOAzureVirtualMachineSize](get-vboazurevirtualmachinesize.md) cmdlet. | False | Named | False |
| RedirectorPort | Specifies a port number. The cmdlet will use this port number to route requests between the archiver appliance and Veeam Backup for Microsoft 365 backup infrastructure components.  Default: 443 | Int32 | False | Named | False |
| ResourceGroup | Specifies a resource group that will be associated with the archiver appliance.  Default: Create new  This value indicates that a new resource group will be created in a region where a container with the specified folder is located when you run the [Add-VBOAzureBlobObjectStorageRepository](add-vboazureblobobjectstoragerepository.md) or [Add-VBOAzureBlobRepository](add-vboazureblobrepository.md) or [Add-VBOAzureArchiveRepository](add-vboazurearchiverepository.md) cmdlet. | Accepts the [VBOAzureResourceGroup](vboazureresourcegroup.md) object.  To get this object, run the [Get-VBOAzureResourceGroup](get-vboazureresourcegroup.md) cmdlet. | False | Named | False |
| VirtualNetwork | Specifies a network to which the archiver appliance will be connected.  Default: Create new  This value indicates that a new virtual network will be created in a region where a container with the specified folder is located when you run the [Add-VBOAzureBlobObjectStorageRepository](add-vboazureblobobjectstoragerepository.md) or [Add-VBOAzureBlobRepository](add-vboazureblobrepository.md) or [Add-VBOAzureArchiveRepository](add-vboazurearchiverepository.md) cmdlet. | Accepts the [VBOAzureVirtualNetwork](vboazurevirtualnetwork.md) object.  To get this object, run the [Get-VBOAzureVirtualNetwork](get-vboazurevirtualnetwork.md) cmdlet. | False | Named | False |
| Subnet | Specifies the archiver appliance subnet.  Default: Create new  This value indicates that a new subnet will be created in a region where a container with the specified folder is located when you run the [Add-VBOAzureBlobObjectStorageRepository](add-vboazureblobobjectstoragerepository.md) or [Add-VBOAzureBlobRepository](add-vboazureblobrepository.md) or [Add-VBOAzureArchiveRepository](add-vboazurearchiverepository.md) cmdlet. | Accepts the [VBOAzureSubnet](vboazuresubnet.md) object.  To get this object, run the [Get-VBOAzureSubNet](get-vboazuresubnet.md) cmdlet. | False | Named | False |
| IpRanges | Specifies a range of IPv4 addresses for the specified subnet. | String[] | True | Named | False |
| ProxyIpRange | Specifies public IPv4 address of a backup proxy server. | Accepts the [VBOProxy](vboproxy.md) object.  To get this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | True | Named | False |
| ProxyPoolIpRange | Specifies public IPv4 addresses of all backup proxy servers added to a backup proxy pool. | Accepts the [VBOProxyPool](vboproxypool.md) object.  To get this object, run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAzureArchiverAppliance](vboazurearchiverappliance.md) object that contains the Azure archiver appliance settings.

Example

Creating Azure Archiver Appliance

This example shows how to define the Azure archiver appliance settings.

|  |
| --- |
| $azureacc = Get-VBOAzureServiceAccount -Id f8e5ac3d-d883-4dd8-8de3-a8f315fb6ae2  $subscription = Get-VBOAzureSubscription -ServiceAccount $azureacc -Id "06b7354e-518f-4a10-b4c1-98f49d743012"  $location = Get-VBOAzureLocation -Subscription $subscription -Name westeurope  $VMsize = Get-VBOAzureVirtualMachineSize -Subscription $subscription -Location $location -Name Standard\_F8s\_v2  $rgroup = Get-VBOAzureResourceGroup -Subscription $subscription -Name "ResourceGroupName"  $VN = Get-VBOAzureVirtualNetwork -ResourceGroup $rgroup -Name "VirtualNetworkName"  $subnet = Get-VBOAzureSubNet -VirtualNetwork $VN -Name "SubnetName"  New-VBOAzureArchiverAppliance -VmSize $VMsize -RedirectorPort 80 -ResourceGroup $rgroup -VirtualNetwork $VN -Subnet $subnet -IpRanges @("217.113.11.0/24","124.31.42.18") |

Perform the following steps:

1. Run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $azureacc variable.
2. Run the [Get-VBOAzureSubscription](get-vboazuresubscription.md) cmdlet. Set the $azureacc variable as the ServiceAccount parameter value. Specify the Id parameter value. Save the result to the $subscription variable.
3. Run the [Get-VBOAzureLocation](get-vboazurelocation.md) cmdlet. Specify the $subscription variable as the Subscription parameter value. Specify the Name parameter value. Save the result to the $location variable.
4. Run the [Get-VBOAzureVirtualMachineSize](get-vboazurevirtualmachinesize.md) cmdlet. Specify the $subscription variable as the Subscription parameter value and the $location as the Location parameter value. Specify the Name parameter value. Save the result to the $VMsize variable.
5. Run the [Get-VBOAzureResourceGroup](get-vboazureresourcegroup.md) cmdlet. Specify the $subscription variable as the Subscription parameter value. Specify the Name parameter value. Save the result to the $rgroup variable.
6. Run the [Get-VBOAzureVirtualNetwork](get-vboazurevirtualnetwork.md) cmdlet. Specify the $rgroup variable as the ResourceGroup parameter value. Specify the Name parameter value. Sane the result to the $VN variable.
7. Run the [Get-VBOAzureSubNet](get-vboazuresubnet.md) cmdlet. Specify the $VN variable as the VirtualNetwork parameter value. Specify the Name parameter value. Save the result to the $subnet variable.
8. Run the New-VBOAzureArchiverAppliance cmdlet. Specify the following settings:

* Set the $VMsize variable as the VmSize parameter value.
* Set the $rgroup variable as the ResourceGroup parameter value.
* Set the $VN variable as the VirtualNetwork parameter value.
* Set the $subnet variable as the Subnet parameter value.
* Specify the RedirectorPort parameter value.
* Specify the IpRanges parameter value.

Related Commands

* [Get-VBOAzureVirtualMachineSize](get-vboazurevirtualmachinesize.md)
* [Get-VBOAzureResourceGroup](get-vboazureresourcegroup.md)
* [Get-VBOAzureSubNet](get-vboazuresubnet.md)
* [Get-VBOAzureVirtualNetwork](get-vboazurevirtualnetwork.md)

* [Get-VBOAzureSubscription](get-vboazuresubscription.md)
* [Get-VBOAzureLocation](get-vboazurelocation.md)
* [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md)
* [Get-VBOProxy](get-vboproxy.md)
* [Get-VBOProxyPool](get-vboproxypool.md)


