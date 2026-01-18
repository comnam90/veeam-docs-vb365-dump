---
title: "VBOAzureSubnet"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboazuresubnet.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBOAzureSubnet


Contains details about a subnet.

| Property | Type | Description |
| --- | --- | --- |
| Name | String | Subnet name. |
| AddressPrefix | String | Range of IPv4 addresses. |
| AzureVirtualNetwork | [VBOAzureVirtualNetwork](vboazurevirtualnetwork.md) | Details about a network to which the archiver appliance is connected. |
| AzureResourceGroup | [VBOAzureResourceGroup](vboazureresourcegroup.md) | Details about a resource group. |
| AzureSubscription | [VBOAzureSubscription](vboazuresubscription.md) | Details about a Microsoft Azure subscription. |
| AzureServiceAccount | [VBOAzureServiceAccount](vboazureserviceaccount.md) | Details about a Microsoft Azure service account. |

Related Commands

* [New-VBOAzureArchiverAppliance](new-vboazurearchiverappliance.md)
* [Get-VBOAzureSubNet](get-vboazuresubnet.md)


