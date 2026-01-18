---
title: "VBOAzureVirtualNetwork"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboazurevirtualnetwork.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBOAzureVirtualNetwork


Contains details about a network to which the Azure archiver appliance is connected.

| Property | Type | Description |
| --- | --- | --- |
| Id | String | Virtual network ID. |
| Name | String | Virtual network name. |
| Type | String | Virtual network type. |
| Location | String | Name of the Microsoft Entra region. |
| AzureResourceGroup | [VBOAzureResourceGroup](vboazureresourcegroup.md) | Details about a resource group. |
| AzureSubscription | [VBOAzureSubscription](vboazuresubscription.md) | Details about a Microsoft Azure subscription. |
| AzureServiceAccount | [VBOAzureServiceAccount](vboazureserviceaccount.md) | Details about a Microsoft Azure service account. |

Related Commands

* [New-VBOAzureArchiverAppliance](new-vboazurearchiverappliance.md)
* [Get-VBOAzureSubNet](get-vboazuresubnet.md)
* [Get-VBOAzureVirtualNetwork](get-vboazurevirtualnetwork.md)


