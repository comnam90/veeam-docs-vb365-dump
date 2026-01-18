---
title: "VBOAzureBlobObjectStorageApplianceInfo"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboazureblobobjectstorageapplianceinfo.html"
last_updated: "1/16/2026"
product_version: "8.3.0.2201"
---

# VBOAzureBlobObjectStorageApplianceInfo


Contains details about the Azure archiver appliance. See also [VBOAzureBlobObjectStorageRepository](vboazureblobobjectstoragerepository.md).

| Property | Type | Description |
| --- | --- | --- |
| ServiceAccountId | GUID | Microsoft Azure service account ID. |
| SubscriptionId | String | Microsoft Azure subscription ID. |
| VmSize | String | Size of the Azure archiver appliance. |
| Region | String | Microsoft Entra region. |
| ResourceGroup | String | Resource group. |
| Subnet | String | Subnet. |
| VirtualNetworkId | String | Virtual network ID. |
| Port | Int | Port number. |
| UseShared | Bool | If True, the Azure archiver appliance uses existing shared Azure resources. |
| IpRanges | String[] | Range of IPv4 addresses. |


