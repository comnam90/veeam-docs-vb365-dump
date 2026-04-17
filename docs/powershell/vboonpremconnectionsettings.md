---
title: "VBOOnPremConnectionSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboonpremconnectionsettings.html"
last_updated: "3/12/2026"
product_version: "8.4.0.1457"
---

# VBOOnPremConnectionSettings


Contains details about connection settings to access the on-premises Microsoft organization.

VBOOnPremConnectionSettings

| Property | Type | Description |
| ServerName | String | Name of the on-premises Microsoft server. |
| SSLUsed | Bool | If True, the SSL encryption is enabled. |
| CAVerificationSkipped | Bool | If True, the certificate trusted authority verification is skipped. |
| CommonNameVerificationSkipped | Bool | If True, the certificate common name verification is skipped. |
| RevocationCheckSkipped | Bool | If True, the certificate revocation check is skipped. |
| UserName | String | User name of the account used for authentication to the on-premises Microsoft organization. |

Related Commands

* [New-VBOOnPremConnectionSettings](new-vboonpremconnectionsettings.md)
* [Set-VBOOnPremConnectionSettings](set-vboonpremconnectionsettings.md)


