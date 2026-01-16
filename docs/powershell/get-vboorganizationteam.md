---
title: "get-vboorganizationteam"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboorganizationteam.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns organization teams.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get all teams of the specified organization.

|  |
| --- |
| Get-VBOOrganizationTeam -Organization <VBOOrganization> [-NotInJob] [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

* Get organization teams by ID.

|  |
| --- |
| Get-VBOOrganizationTeam -Organization <VBOOrganization> [-Id <Guid>] [-NotInJob] [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

* Get organization teams by display name.

|  |
| --- |
| Get-VBOOrganizationTeam -Organization <VBOOrganization> [-DisplayName <String>] [-NotInJob] [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

Detailed Description

This cmdlet returns organization teams.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will return teams of the specified organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| NotInJob | Defines that the cmdlet will return teams that are not manually included in any of the backup jobs.  Default: False  Note: If a team is backed up by the EntireOrganization job, it also will be considered as not included in backups jobs. | SwitchParameter | False | Named | False |
| DataSource | Specifies how the cmdlet will return organization teams:   * PreferLocal   For Microsoft organizations with modern app-only authentication, the cmdlet will return data from either the organization cache database if organization objects are already synchronized to this source, or directly from the organization if synchronization is in progress.  For Microsoft organizations with modern authentication and legacy protocols or with basic authentication, the cmdlet will return data directly from the organization.   * Production   The cmdlet will return data directly from the organization.   * PreferLocalResynced   For Microsoft organizations with modern app-only authentication, the cmdlet will start synchronization of objects with the organization cache database and upon synchronization completes, it returns data from the organization cache database.  For Microsoft organizations with modern authentication and legacy protocols or with basic authentication, the cmdlet will return data directly from the organization.  Default: PreferLocal | VBOOrganizationDataSource | False | Named | False |
| Id | Specifies an ID of the team. The cmdlet will return the team with the specified ID. | Guid | False | Named | False |
| DisplayName | Specifies a display name of the team. The cmdlet will return the team with the specified display name. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Unprocessed Teams in Microsoft Organization

|  |  |
| --- | --- |
| This example shows how to get all organization teams for an organization with the name ABC that are not backed up by any job.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOOrganizationTeam -Organization $org -NotInJob |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBOOrganizationTeam cmdlet. Set the $org variable as the Organization parameter value. Provide the NotInJob parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Specific Team by ID

|  |  |
| --- | --- |
| This example shows how to get a team with the ID 47972f7d-05c4-43b5-95f7-60735ee56006 for an organization with the name ABC.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOOrganizationTeam -Organization $org -Id 47972f7d-05c4-43b5-95f7-60735ee56006 |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get an organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBOOrganizationTeam cmdlet. Set the $org variable as the Organization parameter value. Specify the Id parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Specific Team by Display Name

|  |  |
| --- | --- |
| This example shows how to get a team with the display name IT for an organization with the name ABC.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOOrganizationTeam -Organization $org -DisplayName "IT" |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get an organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBOOrganizationTeam cmdlet. Set the $org variable as the Organization parameter value. Specify the DisplayName parameter value. |

Related Commands

[Get-VBOOrganization](get-vboorganization.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
