---
title: "VBORestAPISettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vborestapisettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBORestAPISettings


Contains details about REST API settings.

| Property | Type | Description |
| --- | --- | --- |
| IsServiceEnabled | Bool | If True, Veeam Backup for Microsoft 365 REST API Service is enabled. |
| AuthTokenLifeTime | Int | Lifetime value for the authentication token. |
| HTTPSPort | Int | Port number for server-client communication over HTTPS protocol. |
| CertificateIssuedTo | String | Authority for whom the SSL certificate is issued. |
| CertificateIssuedBy | String | Authority issued the SSL certificate. |
| CertificateFriendlyName | String | SSL certificate name. |
| CertificateExpirationDate | DateTime | Date and time when the SSL certificate expires. |
| CertificateThumbprint | String | Certificate thumbprint. |
| EnableSwaggerUI | Bool | If True, access to the swagger website and usage of Swagger UI is enabled. |
| EnableOperatorAuthenticationOnly | Bool | If True, REST API is used only for authentication of restore operators to Restore Portal. |

Related Commands

* [Get-VBORestAPISettings](get-vborestapisettings.md)
* [Set-VBORestAPISettings](set-vborestapisettings.md)


