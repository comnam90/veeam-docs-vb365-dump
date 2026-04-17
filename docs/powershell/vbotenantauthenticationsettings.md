---
title: "VBOTenantAuthenticationSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbotenantauthenticationsettings.html"
last_updated: "3/12/2026"
product_version: "8.4.0.1457"
---

# VBOTenantAuthenticationSettings


Contains details about the Veeam Backup for Microsoft 365 tenant authentication settings.

VBOTenantAuthenticationSettings

| Property | Type | Description |
| AuthenticationEnabled | Bool | If True, tenant authentication to the Veeam Backup for Microsoft 365 server is enabled. |
| CertificateIssuedTo | String | Authority for whom the TLS certificate is issued. |
| CertificateIssuedBy | String | Authority issued the TLS certificate. |
| CertificateFriendlyName | String | TLS certificate name. |
| CertificateExpirationDate | DateTime | Date and time when the TLS certificate expires. |
| CertificateThumbprint | String | Certificate thumbprint. |

Related Commands

* [Get-VBOTenantAuthenticationSettings](get-vbotenantauthenticationsettings.md)
* [Set-VBOTenantAuthenticationSettings](set-vbotenantauthenticationsettings.md)


