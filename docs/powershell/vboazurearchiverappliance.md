---
title: "VBOAzureArchiverAppliance"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboazurearchiverappliance.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBOAzureArchiverAppliance


Contains details about the Azure archiver appliance.

| Property | Type | Description |
| --- | --- | --- |
| VmSize | [VBOAzureVirtualMachineSize](vboazurevirtualmachinesize.md) | Details about a size of the Azure archiver appliance. |
| ResourceGroup | [VBOAzureResourceGroup](vboazureresourcegroup.md) | Details about a resource group associated with the archiver appliance. |
| VirtualNetwork | [VBOAzureVirtualNetwork](vboazurevirtualnetwork.md) | Details about a network to which the archiver appliance is connected. |
| Subnet | [VBOAzureSubnet](vboazuresubnet.md) | Details about the archiver appliance subnet. |
| RedirectorPort | Int | Port number. |
| IpRanges | String[] | Range of IPv4 addresses. |

Related Commands

* [Set-VBOAzureBlobRepository](set-vboazureblobrepository.md)
* [Set-VBOAzureArchiveRepository](set-vboazurearchiverepository.md)
* [New-VBOAzureBlobObjectStorageSettings](new-vboazureblobobjectstoragesettings.md)
* [Add-VBOAzureBlobObjectStorageRepository](add-vboazureblobobjectstoragerepository.md)
* [Set-VBOObjectStorageRepository](set-vboobjectstoragerepository.md)
* [New-VBOAzureArchiverAppliance](new-vboazurearchiverappliance.md)


