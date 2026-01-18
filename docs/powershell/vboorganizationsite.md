---
title: "VBOOrganizationSite"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboorganizationsite.html"
last_updated: "1/7/2026"
product_version: "8.3.0.2201"
---

# VBOOrganizationSite


Contains details about an organization site.

| Property | Type | Description |
| --- | --- | --- |
| OrganizationId | GUID | Microsoft organization ID. |
| SiteId | GUID | ID of the organization site. |
| WebId | GUID | ID of the subsite. |
| Name | String | Name of the organization site. |
| URL | String | Path to the organization site. |
| IsCloud | Bool | If True, the organization site is located in cloud. |
| ParentURL | String | Path for the parent object. |
| IsAvailable | Bool | If True, the organization site is available for backup and restore. |
| SiteCollectionError | String | Error occurred when processing site collections. |

Related Commands

* [New-VBOBackupItem](new-vbobackupitem.md)
* [Get-VBOOrganizationSite](get-vboorganizationsite.md)
* [New-VBORbacRoleItem](new-vborbacroleitem.md)
* [Get-VBOEntityData](get-vboentitydata.md)


