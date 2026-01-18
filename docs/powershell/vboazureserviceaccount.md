---
title: "VBOAzureServiceAccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboazureserviceaccount.html"
last_updated: "12/19/2025"
product_version: "8.3.0.2201"
---

# VBOAzureServiceAccount


Contains details about a Microsoft Azure service account.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Microsoft Azure service account ID. |
| Region | VBOAzureRegionType | Microsoft Entra region. Possible values:   * Global * Germany * China * Government |
| TenantId | String | Microsoft 365 organization ID in Microsoft Entra. |
| Name | String | Name of Microsoft Entra application associated with the Microsoft Azure service account. |
| ApplicationId | GUID | Microsoft Entra application ID. |
| Description | String | Description of the Microsoft Azure service account. |
| ApplicationCertificateThumbprint | String | Application certificate thumbprint for connecting to Microsoft Entra. |
| LastModified | DateTime | Date and time when the Microsoft Azure service account was last modified. |

Related Commands

* [Add-VBOAzureServiceAccount](add-vboazureserviceaccount.md)
* [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md)
* [Set-VBOAzureServiceAccount](set-vboazureserviceaccount.md)
* [Remove-VBOAzureServiceAccount](remove-vboazureserviceaccount.md)
* [Get-VBOAzureSubscription](get-vboazuresubscription.md)


