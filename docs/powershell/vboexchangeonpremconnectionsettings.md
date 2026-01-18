---
title: "VBOExchangeOnPremConnectionSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboexchangeonpremconnectionsettings.html"
last_updated: "1/7/2026"
product_version: "8.3.0.2201"
---

# VBOExchangeOnPremConnectionSettings


Contains details about connection settings to access the Microsoft on-premises Exchange organization.

| Property | Type | Description |
| --- | --- | --- |
| UserAccountConfigured | Bool? | If True, the user account is assigned the ApplicationImpersonation role. |
| ThrottlingPolicyConfigured | Bool? | If True, the default Exchange throttling policy is skipped and the VeeamArchiverThrottlingPolicy is used that provides unlimited network bandwidth. |

Related Commands

* [Add-VBOOrganization](add-vboorganization.md)
* [Set-VBOOrganization](set-vboorganization.md)


