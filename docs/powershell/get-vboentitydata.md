---
title: "get-vboentitydata"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboentitydata.html"
last_updated: "2/18/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns a user, group, site, team or organization backed-up data.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get backed-up data by the associated backup repository and a type of the entity data.

|  |
| --- |
| Get-VBOEntityData -Repository <VBORepository> -Type <VBOEntityDataType> [-Name <String>] [-Organization <VBOOrganization>] [<CommonParameters>] |

* Get a specific Microsoft organization backed-up data by the associated backup repository.

|  |
| --- |
| Get-VBOEntityData -Repository <VBORepository> -Organization <VBOOrganization> [<CommonParameters>] |

* Get a specific user backed-up data by the associated backup repository.

|  |
| --- |
| Get-VBOEntityData -Repository <VBORepository> -User <VBOOrganizationUser> [<CommonParameters>] |

* Get a specific group backed-up data by the associated backup repository.

|  |
| --- |
| Get-VBOEntityData -Repository <VBORepository> -Group <VBOOrganizationGroup> [<CommonParameters>] |

* Get a specific SharePoint site backed-up data by the associated backup repository.

|  |
| --- |
| Get-VBOEntityData -Repository <VBORepository> -Site <VBOOrganizationSite> [<CommonParameters>] |

* Get a specific team backed-up data by the associated backup repository.

|  |
| --- |
| Get-VBOEntityData -Repository <VBORepository> -Team <VBOOrganizationTeam> [<CommonParameters>] |

* Get backed-up data by a type of the entity data from a specific restore point.

|  |
| --- |
| Get-VBOEntityData -Type <VBOEntityDataType> [-Name <String>] -RestorePoint <VBORestorePoint> [<CommonParameters>] |

Detailed Description

This cmdlet returns a representation entity of the backed-up data of an organization user, organization group, organization site, organization team, or an organization itself. You can use it with the [Move-VBOEntityData](move-vboentitydata.md) or [Remove-VBOEntityData](remove-vboentitydata.md) cmdlets.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Repository | Specifies a backup repository. The cmdlet will return backed-up data from this backup repository. | Accepts the VBORepository object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | True (ByValue) |
| Type | Specifies a type of the entity data. The cmdlet will return backed-up data for the entity of this type. You can select the following entity data types:   * User * Group * Site * Team * Organization * OneDrive * Mailbox   Note: The OneDrive and Mailbox entity data types can be used only for the object storage repository that was specified as a target for backup copy jobs. | VBOEntityDataType | True | Named | False |
| Name | Specifies a name filter for the searched data. The cmdlet will return a collection of data with the specified name. | String | False | Named | False |
| Organization | Specifies a Microsoft organization. The cmdlet will return backed-up data for this organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | False | Named | False |
| User | Specifies an organization user. The cmdlet will return backed-up data for this user. | Accepts the VBOOrganizationUser object.  To get this object, run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet. | True | Named | False |
| Group | Specifies an organization group. The cmdlet will return backed-up data for this group. | Accepts the VBOOrganizationGroup object.  To get this object, run the [Get-VBOOrganizationGroup](get-vboorganizationgroup.md) cmdlet. | True | Named | False |
| Site | Specifies a SharePoint site. The cmdlet will return backed-up data for this site. | Accepts the VBOOrganizationSite object.  To get this object, run the [Get-VBOOrganizationSite](get-vboorganizationsite.md) cmdlet. | True | Named | False |
| Team | Specifies an organization team. The cmdlet will return backed-up data for this team. | Accepts the VBOOrganizationTeam object.  To get this object, run the [Get-VBOOrganizationTeam](get-vboorganizationteam.md) cmdlet. | True | Named | False |
| RestorePoint | Specifies a restore point stored in Veeam Backup for Microsoft 365. The cmdlet will return backed-up data from this restore point. | Accepts the VBORestorePoint object.  To get this object, run the [Get-VBORestorePoint](get-vborestorepoint.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Getting Backed-Up Data of Specific User

This example shows how to get backed-up data of a user with the name Chuck Brown.

|  |
| --- |
| $repository = Get-VBORepository -Name "ABC Daily Backup"  Get-VBOEntityData -Repository $repository -Type User -Name "Chuck Brown" |

Perform the following steps:

1. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get the backup repository. Save the result to the $repository variable.
2. Run the Get-VBOEntityData cmdlet with the $repository variable and Name parameter to get backed-up data of a user with the name Chuck Brown.

Related Commands

* [Move-VBOEntityData](move-vboentitydata.md)
* [Remove-VBOEntityData](remove-vboentitydata.md)
* [Get-VBORepository](get-vborepository.md)
* [Get-VBOOrganizationUser](get-vboorganizationuser.md)
* [Get-VBOOrganizationTeam](get-vboorganizationteam.md)
* [Get-VBOOrganizationSite](get-vboorganizationsite.md)
* [Get-VBORestorePoint](get-vborestorepoint.md)
* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationGroup](get-vboorganizationgroup.md)

Page updated 2/18/2025

Page content applies to build 8.3.0.2201
