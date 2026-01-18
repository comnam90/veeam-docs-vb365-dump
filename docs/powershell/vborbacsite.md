---
title: "VBORbacSite"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vborbacsite.html"
last_updated: "1/9/2026"
product_version: "8.3.0.2201"
---

# VBORbacSite


Contains details about a site that is managed by restore operators or is excluded. See also [VBORbacRoleItem](vborbacroleitem.md).

| Property | Type | Description |
| --- | --- | --- |
| SiteId | GUID | ID of the organization site. |
| WebId | GUID | ID of the subsite. |
| URL | String | Path to the organization site. |
| Title | String | Title of the site. |
| ParentURL | String | Path for the parent object. |
| IsCloud | Bool | If True, the organization site is located in cloud. |
| IsPersonal | Bool | If True, the organization site is personal. |

Related Commands

* [New-VBORbacRoleItem](new-vborbacroleitem.md)
* [Add-VBORbacRole](add-vborbacrole.md)
* [Set-VBORbacRole](set-vborbacrole.md)


