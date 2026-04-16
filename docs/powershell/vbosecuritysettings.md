---
title: "VBOSecuritySettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbosecuritysettings.html"
last_updated: "3/12/2026"
product_version: "8.4.0.1457"
---

# VBOSecuritySettings


Contains details about security settings.

VBOSecuritySettings

| Property | Type | Description |
| CertificateIssuedTo | String | Authority for whom the TLS certificate is issued. |
| CertificateIssuedBy | String | Authority issued the TLS certificate. |
| CertificateFriendlyName | String | TLS certificate name. |
| CertificateExpirationDate | DateTime | Date and time when the TLS certificate expires. |
| CertificateThumbprint | String | Certificate thumbprint. |

Related Commands

* [Get-VBOSecuritySettings](get-vbosecuritysettings.md)
* [Set-VBOSecuritySettings](set-vbosecuritysettings.md)


