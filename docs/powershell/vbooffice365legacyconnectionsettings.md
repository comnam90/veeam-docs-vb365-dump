---
title: "VBOOffice365LegacyConnectionSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbooffice365legacyconnectionsettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOOffice365LegacyConnectionSettings


Contains details about connection settings to access the Microsoft 365 organization.

| Property | Type | Description |
| --- | --- | --- |
| AuthenticationType | VBOOffice365AuthenticationType | Authentication type. Possible values:   * Basic * Modern * ApplicationOnly |
| RolesAndPermissionsGranted | Bool | If True, the user account is granted required permissions and assigned appropriate roles. |
| UserName | String | Name of the user account to connect to a Microsoft 365 organization. |

Related Commands

* [New-VBOOffice365ConnectionSettings](new-vbooffice365connectionsettings.md)
* [Set-VBOOffice365ConnectionSettings](set-vbooffice365connectionsettings.md)


