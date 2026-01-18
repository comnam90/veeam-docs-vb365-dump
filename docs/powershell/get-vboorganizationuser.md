---
title: "Get-VBOOrganizationUser"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboorganizationuser.html"
last_updated: "1/6/2026"
product_version: "8.3.0.2201"
---

# Get-VBOOrganizationUser


Short Description

Returns organization users.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get organization users of the specified type.

|  |
| --- |
| Get-VBOOrganizationUser -Organization <VBOOrganization> [-Limit <UInt64>] [-Type <VBOOrganizationUserType>] [-NotInJob] [-LocationFilter <VBOLocationFilters>] [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

* Get organization users by name.

|  |
| --- |
| Get-VBOOrganizationUser -Organization <VBOOrganization> [-Name <String>] [-UserName <String>] [-DisplayName <String>] [-Limit <UInt64>] [-Type <VBOOrganizationUserType>] [-NotInJob] [-LocationFilter <VBOLocationFilters>] [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

* Get organization users by ID.

|  |
| --- |
| Get-VBOOrganizationUser -Organization <VBOOrganization> [-OfficeId <Guid>] [-OnPremisesId <Guid>] [-Type <VBOOrganizationUserType>] [-NotInJob] [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

Detailed Description

This cmdlet returns Microsoft organization users.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will return organization users of the specified organization. | Accepts the [VBOOrganization](vboorganization.md) object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| Limit | Specifies the maximum number of users that the cmdlet will return. | UInt64 | False | Named | False |
| Type | Specifies the organization user type:   * User * SharedMailbox * PublicMailbox   The cmdlet will return organization users of this type.  Note: To get shared or public mailboxes in Microsoft organizations with modern app-only authentication, you must specify the User type. For more information, see [this Veeam KB article](https://www.veeam.com/kb3146). | VBOOrganizationUserType | False | Named | False |
| NotInJob | Defines that the cmdlet will return users that are not manually included in any of the backup jobs.  Default: False  Note: If a user is backed up by the EntireOrganization job, it also will be considered as not included in backups jobs. | SwitchParameter | False | Named | False |
| LocationFilter | Note: Use this parameter for organizations of the Hybrid type.  Specifies an organization user location type:   * Cloud * OnPremises * Hybrid * CloudOrHybrid * OnPremisesOrHybrid * Any   The cmdlet will return organization users of this location type. | VBOLocationFilters | False | Named | False |
| DataSource | Specifies how the cmdlet will return organization users:   * PreferLocal   For Microsoft organizations with modern app-only authentication, the cmdlet will return data from either the organization cache database if organization objects are already synchronized to this source, or directly from the organization if synchronization is in progress.  For Microsoft organizations with modern authentication and legacy protocols or with basic authentication, the cmdlet will return data directly from the organization.   * Production   The cmdlet will return data directly from the organization.   * PreferLocalResynced   For Microsoft organizations with modern app-only authentication, the cmdlet will start synchronization of objects with the organization cache database and upon synchronization completes, it returns data from the organization cache database.  For Microsoft organizations with modern authentication and legacy protocols or with basic authentication, the cmdlet will return data directly from the organization.  Default: PreferLocal | VBOOrganizationDataSource | False | Named | False |
| Name | Note: This parameter is deprecated. Use the UserName or DisplayName parameter instead.  Specifies a name of an organization user. The cmdlet will return the organization user with this name. | String | False | Named | False |
| UserName | Specifies a user name of an organization user. The cmdlet will return the organization user with this user name. | String | False | Named | False |
| DisplayName | Specifies a display name of an organization user. The cmdlet will return the organization user with this display name. | String | False | Named | False |
| OfficeId | Specifies an ID of a Microsoft 365 organization user. The cmdlet will return the organization user with this ID. | Guid | False | Named | False |
| OnPremisesId | Specifies an ID of an on-premises organization user. The cmdlet will return the organization user with this ID. | Guid | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns an array of the [VBOOrganizationUser](vboorganizationuser.md) objects that contain details about Microsoft organization users.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Users in Microsoft Organization

|  |  |
| --- | --- |
| This example shows how to get all organization users in the ABC organization.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOOrganizationUser -Organization $org |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBOrganizationUser cmdlet with the $org variable to get all organization users of an organization with the name ABC. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Users of Specific Type

|  |  |
| --- | --- |
| This example shows how to get all organization users of the User type in the ABC organization.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOOrganizationUser -Organization $org -Type User |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBOrganizationUser cmdlet with the $org variable to get all organization users of an organization with the name ABC. Use the Type parameter to select only the specified type of the organization users. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Specific User

|  |  |
| --- | --- |
| This example shows how to get the userAlpha organization user by the user display name.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOOrganizationUser -Organization $org -DisplayName "userAlpha" |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBOOrganizationUser cmdlet with the $org variable. Set the userAlpha value for the DisplayName parameter to get an organization user with the display name userAlpha. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Getting Unprocessed Users Using Wildcards

|  |  |
| --- | --- |
| This example shows how to get all users of the User type with a display name starting with A that are not manually included in any of backup jobs.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOOrganizationUser -Organization $org -DisplayName "A\*" -Type User -NotInJob |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBOOrganizationUser cmdlet with the $org variable. Set the A\* value for the DisplayName parameter, the User value for the Type parameter to get all organization users of the User type with a display name starting with A. Use the NotInJob parameter to get only organization users that are not manually included in any of backup jobs. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 5: Getting User by User Name

|  |  |
| --- | --- |
| This example shows how to get the userAlpha@tech.onmicrosoft.com organization user by the user name.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOOrganizationUser -Organization $org -UserName "userAlpha@tech.onmicrosoft.com" |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBOOrganizationUser cmdlet with the $org variable and the userAlpha@tech.onmicrosoft.com value for the UserName parameter. |

Related Commands

[Get-VBOOrganization](get-vboorganization.md)


