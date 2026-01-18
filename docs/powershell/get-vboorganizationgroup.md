---
title: "Get-VBOOrganizationGroup"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboorganizationgroup.html"
last_updated: "12/17/2025"
product_version: "8.3.0.2201"
---

# Get-VBOOrganizationGroup


Short Description

Returns organization groups.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get organization groups.

|  |
| --- |
| Get-VBOOrganizationGroup -Organization <VBOOrganization> [-Limit <UInt64>] [-Type <VBOOrganizationGroupType>] [-NotInJob] [-LocationFilter <VBOLocationFilters>] [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

* Get organization groups by name.

|  |
| --- |
| Get-VBOOrganizationGroup -Organization <VBOOrganization> [-Name <String>] [-DisplayName <String>] [-GroupName <String>] [-Limit <UInt64>] [-Type <VBOOrganizationGroupType>] [-NotInJob] [-LocationFilter <VBOLocationFilters>] [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

* Get organization groups by ID.

|  |
| --- |
| Get-VBOOrganizationGroup -Organization <VBOOrganization> [-OfficeId <Guid>] [-OnPremisesId <Guid>] [-Type <VBOOrganizationGroupType>] [-NotInJob] [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

Detailed Description

This cmdlet returns Microsoft Exchange and Microsoft SharePoint organization groups.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will return organization groups of the specified organization. | Accepts the [VBOOrganization](vboorganization.md) object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| Limit | Specifies the maximum number of groups that the cmdlet will return. | UInt64 | False | Named | False |
| Type | Specifies the organization group type:   * Office 365 * Security * Distribution * DynamicDistribution   The cmdlet will return organization groups of this type.  Note: The cmdlet will not return organization groups of an on-premises organization with SharePoint components. | VBOOrganizationGroupType | False | Named | False |
| NotInJob | Defines that the cmdlet will return groups that are not manually included in any of the backup jobs.  Default: False  Note: If a group is backed up by the EntireOrganization job, it also will be considered as not included in backups jobs. | SwitchParameter | False | Named | False |
| LocationFilter | Note: Use this parameter for organizations of the Hybrid type.  Specifies an organization group location type:   * Cloud * OnPremises * Hybrid * CloudOrHybrid * OnPremisesOrHybrid * Any   The cmdlet will return organization groups of this location type. | VBOLocationFilters | False | Named | False |
| DataSource | Specifies how the cmdlet will return organization groups:   * PreferLocal   For Microsoft organizations with modern app-only authentication, the cmdlet will return data from either the organization cache database if organization objects are already synchronized to this source, or directly from the organization if synchronization is in progress.  For Microsoft organizations with modern authentication and legacy protocols or with basic authentication, the cmdlet will return data directly from the organization.   * Production   The cmdlet will return data directly from the organization.   * PreferLocalResynced   For Microsoft organizations with modern app-only authentication, the cmdlet will start synchronization of objects with the organization cache database and upon synchronization completes, it returns data from the organization cache database.  For Microsoft organizations with modern authentication and legacy protocols or with basic authentication, the cmdlet will return data directly from the organization.  Default: PreferLocal | VBOOrganizationDataSource | False | Named | False |
| Name | Note: This parameter is deprecated. Use the DisplayName instead.  Specifies a name of an organization group. The cmdlet will return organization groups with this name. | String | False | Named | False |
| DisplayName | Specifies a display name of an organization group. The cmdlet will return organization groups with this display name. | String | False | Named | False |
| GroupName | Specifies a group name of an organization group. The cmdlet will return the organization group with this group name. | String | False | Named | False |
| OfficeId | Specifies ID of a Microsoft 365 organization group. The cmdlet will return the organization group with this ID. | Guid | False | Named | False |
| OnPremisesId | Specifies ID of an on-premises organization group. The cmdlet will return the organization group with this ID. | Guid | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns an array of the [VBOOrganizationGroup](vboorganizationgroup.md) objects that contain details about Microsoft Exchange and Microsoft SharePoint organization groups.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Groups in Microsoft Organization

|  |  |
| --- | --- |
| This example shows how to get all organization groups in the ABC organization.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOOrganizationGroup -Organization $org |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBOOrganizationGroup cmdlet with the $org variable to get all organization groups of an organization with the name ABC. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Specific Group

|  |  |
| --- | --- |
| This example shows how to get an organization group with the display name UsersAlpha from the ABC organization.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOOrganizationGroup -Organization $org -DisplayName "UsersAlpha" |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBOOrganizationGroup cmdlet with the $org variable and the DisplayName parameter to get an organization group with the display name UsersAlpha. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Groups of Specific Type

|  |  |
| --- | --- |
| This example shows how to get all organization groups with a display name starting with A of the Office365 type that are not manually included in any of backup jobs.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOOrganizationGroup -Organization $org -DisplayName "A\*" -Type Office365 -NotInJob |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBOOrganizationGroup cmdlet with the $org variable, the DisplayName parameter and the specified Type parameter to get an organization group of the Office365 type with a display name starting with A. Use the NotInJob parameter to get only organization groups that are not manually included in any of backup jobs. |

Related Commands

[Get-VBOOrganization](get-vboorganization.md)


