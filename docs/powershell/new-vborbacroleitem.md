---
title: "new-vborbacroleitem"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vborbacroleitem.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Defines objects that will be managed by restore operators or excluded objects whose backed-up data will not be explored and restored by restore operators.

Syntax

This cmdlet provides parameter sets that allow you to:

* Create objects to manage/exclude that represent users.

|  |
| --- |
| New-VBORbacRoleItem -User <VBOOrganizationUser[]> [<CommonParameters>] |

* Create objects to manage/exclude that represent sites.

|  |
| --- |
| New-VBORbacRoleItem -Site <VBOOrganizationSite[]> [<CommonParameters>] |

* Create objects to manage/exclude that represent groups.

|  |
| --- |
| New-VBORbacRoleItem -Group <VBOOrganizationGroup[]> [<CommonParameters>] |

* Create objects to manage/exclude that represent teams.

|  |
| --- |
| New-VBORbacRoleItem -Team <VBOOrganizationTeam[]> [<CommonParameters>] |

* Create objects to manage/exclude that represent personal sites.

|  |
| --- |
| New-VBORbacRoleItem [-PersonalSites] [<CommonParameters>] |

Detailed Description

This cmdlet creates the VBORbacRoleItem object. This object contains specific users, groups, sites, or teams. Restore operators will be allowed/not allowed to explore and restore data from backups created by Veeam Backup for Microsoft 365 for this object.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| User | Specifies an array of users added to Veeam Backup for Microsoft 365. The cmdlet will define these users as objects to manage/exclude. | Accepts the VBOOrganizationUser[] object.  To get this object, run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet. | True | Named | False |
| Site | Specifies an array of SharePoint sites added to Veeam Backup for Microsoft 365. The cmdlet will define these sites as objects to manage/exclude. | Accepts the VBOOrganizationSite[] object.  To get this object, run the [Get-VBOOrganizationSite](get-vboorganizationsite.md) cmdlet. | True | Named | False |
| Group | Specifies an array of groups added to Veeam Backup for Microsoft 365. The cmdlet will define these groups as objects to manage/exclude. | Accepts the VBOOrganizationGroup[] object.  To get this object, run the [Get-VBOOrganizationGroup](get-vboorganizationgroup.md) cmdlet. | True | Named | False |
| Team | Specifies an array of teams added to Veeam Backup for Microsoft 365. The cmdlet will define these teams as objects to manage/exclude. | Accepts the VBOOrganizationTeam[] object.  To get this object, run the [Get-VBOOrganizationTeam](get-vboorganizationteam.md) cmdlet. | True | Named | False |
| PersonalSites | Defines that the cmdlet will define personal sites as objects to manage/exclude.  Default: False | SwitchParameter | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

This cmdlet returns the VBORbacRoleItem object that contains details on users, groups, or sites that will be managed by restore operators or excluded.

Example

Defining User as Object to Manage/Exclude

This example shows how to define the JohnDoe organization user as an object to manage/exclude.

|  |
| --- |
| $org = Get-VBOOrganization -Name "ABC"  $User = Get-VBOOrganizationUser -Organization $org -DisplayName "JohnDoe"  New-VBORbacRoleItem -User $User |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable.
2. Run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet with the $org variable and the JohnDoe value for the DisplayName parameter. Save the result to the $User variable.
3. Run the New-VBORbacRoleItem cmdlet. Set the $User variable as the User parameter value.

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationUser](get-vboorganizationuser.md)
* [Get-VBOOrganizationGroup](get-vboorganizationgroup.md)
* [Get-VBOOrganizationSite](get-vboorganizationsite.md)
* [Get-VBOOrganizationTeam](get-vboorganizationteam.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
