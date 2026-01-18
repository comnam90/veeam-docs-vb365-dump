---
title: "VBORestorePortalSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vborestoreportalsettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBORestorePortalSettings


Contains details about connection settings to access Restore Portal.

| Property | Type | Description |
| --- | --- | --- |
| IsServiceEnabled | Bool | If True, Restore Portal is enabled. |
| Region | VBOOffice365Region | Microsoft Entra region where Microsoft 365 organization datacenter is located. Possible values:   * Worldwide * Germany * China * USDefence * USGovernment |
| ApplicationId | GUID | Microsoft Entra application ID. |
| PortalUri | String | Web address of a machine with the Veeam Backup for Microsoft 365 REST API component installed. |
| CertificateIssuedTo | String | Authority for whom the SSL certificate is issued. |
| CertificateIssuedBy | String | Authority issued the SSL certificate. |
| CertificateFriendlyName | String | SSL certificate name. |
| CertificateExpirationDate | DateTime | Date and time when the SSL certificate expires. |
| CertificateThumbprint | String | Certificate thumbprint. |

Related Commands

* [Get-VBORestorePortalSettings](get-vborestoreportalsettings.md)
* [Set-VBORestorePortalSettings](set-vborestoreportalsettings.md)


