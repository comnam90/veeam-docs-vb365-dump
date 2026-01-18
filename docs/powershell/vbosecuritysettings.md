---
title: "VBOSecuritySettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbosecuritysettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOSecuritySettings


Contains details about secutity settings.

| Property | Type | Description |
| --- | --- | --- |
| CertificateIssuedTo | String | Authority for whom the SSL certificate is issued. |
| CertificateIssuedBy | String | Authority issued the SSL certificate. |
| CertificateFriendlyName | String | SSL certificate name. |
| CertificateExpirationDate | DateTime | Date and time when the SSL certificate expires. |
| CertificateThumbprint | String | Certificate thumbprint. |

Related Commands

* [Get-VBOSecuritySettings](get-vbosecuritysettings.md)
* [Set-VBOSecuritySettings](set-vbosecuritysettings.md)


