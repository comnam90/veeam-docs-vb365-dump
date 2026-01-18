---
title: "VBOTenantAuthenticationSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbotenantauthenticationsettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOTenantAuthenticationSettings


Contains details about the Veeam Backup for Microsoft 365 tenant authentication settings.

| Property | Type | Description |
| --- | --- | --- |
| AuthenticationEnabled | Bool | If True, tenant authentication to the Veeam Backup for Microsoft 365 server is enabled. |
| CertificateIssuedTo | String | Authority for whom the SSL certificate is issued. |
| CertificateIssuedBy | String | Authority issued the SSL certificate. |
| CertificateFriendlyName | String | SSL certificate name. |
| CertificateExpirationDate | DateTime | Date and time when the SSL certificate expires. |
| CertificateThumbprint | String | Certificate thumbprint. |

Related Commands

* [Get-VBOTenantAuthenticationSettings](get-vbotenantauthenticationsettings.md)
* [Set-VBOTenantAuthenticationSettings](set-vbotenantauthenticationsettings.md)


