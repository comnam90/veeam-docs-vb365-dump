---
title: "get-vboorganizationsite"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboorganizationsite.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns organization sites.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get all organization sites of the specified organization.

|  |
| --- |
| Get-VBOOrganizationSite -Organization <VBOOrganization> [-IncludePersonalSite] [-IncludeSearchSite] [-NotInJob] [-Recurse] [-LocationFilter <VBOSiteLocationFilters>] [-Filter <String>] [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

* Get organization sites by the site URL.

|  |
| --- |
| Get-VBOOrganizationSite -Organization <VBOOrganization> [-URL <String>] [-IncludePersonalSite] [-IncludeSearchSite] [-NotInJob] [-Recurse] [-LocationFilter <VBOSiteLocationFilters>] [-Filter <String>] [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

* Get sub-level child sites of the specified parent organization site.

|  |
| --- |
| Get-VBOOrganizationSite -Organization <VBOOrganization> [-ParentURL <String>] [-IncludePersonalSite] [-IncludeSearchSite] [-NotInJob] [-Recurse] [-LocationFilter <VBOSiteLocationFilters>] [-Filter <String>] [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

Detailed Description

This cmdlet returns Microsoft organization sites.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will return organization sites of the specified organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| IncludePersonalSite | Defines that the cmdlet will return personal sites along with the other organization sites.  Default: False | SwitchParameter | False | Named | False |
| IncludeSearchSite | Defines that the cmdlet will return search sites along with the other organization sites.  Default: False | SwitchParameter | False | Named | False |
| NotInJob | Defines that the cmdlet will return sites that are not manually included in any of the backup jobs.  Default: False  Note: If a site is backed up by the EntireOrganization job, it also will be considered as not included in backups jobs. | SwitchParameter | False | Named | False |
| Recurse | Defines that the cmdlet will return all sub-level child sites.  Default: False | SwitchParameter | False | Named | False |
| LocationFilter | Note: Use this parameter for organizations of the Hybrid type.  Specifies an organization site location type:   * Cloud * OnPremises * Any   The cmdlet will return organization sites of this location type. | VBOSiteLocationFilters | False | Named | False |
| Filter | Specifies a keyword to filter organization sites. The cmdlet will return sites that match this search criterion. | String | False | Named | False |
| DataSource | Specifies how the cmdlet will return organization sites:   * PreferLocal   For Microsoft organizations with modern app-only authentication, the cmdlet will return data from either the organization cache database if organization objects are already synchronized to this source, or directly from the organization if synchronization is in progress.  For Microsoft organizations with modern authentication and legacy protocols or with basic authentication, the cmdlet will return data directly from the organization.   * Production   The cmdlet will return data directly from the organization.   * PreferLocalResynced   For Microsoft organizations with modern app-only authentication, the cmdlet will start synchronization of objects with the organization cache database and upon synchronization completes, it returns data from the organization cache database.  For Microsoft organizations with modern authentication and legacy protocols or with basic authentication, the cmdlet will return data directly from the organization.  Default: PreferLocal | VBOOrganizationDataSource | False | Named | False |
| URL | Specifies the organization site URL.  If the Recurse parameter is not used, the cmdlet will return the organization site with this URL. | String | False | Named | False |
| ParentURL | Specifies parent organization site URL.  If the Recurse parameter is not used, the cmdlet will return one sub-level child site of the organization site with this URL. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Unprocessed Sites in Microsoft Organization

|  |  |
| --- | --- |
| This example shows how to get all organization sites in the ABC organization that are not backed up by any backup job.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOOrganizationSite -Organization $org -NotInJob -IncludePersonalSite |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBOrganizationSite cmdlet with the $org variable to get all organization sites of an organization with the name ABC. Use the NotInJob parameter to get only organization sites that are not manually included in any of backup jobs. Use the IncludePersonalSite parameter to get personal sites as well. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Specific Site Including All Child Sites

|  |  |
| --- | --- |
| This example shows how to get an organization site under a certain URL and all of its child sites.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  $siteUrl = "https://exampleorganization.sharepoint.com/sites/exampleparentsite"  Get-VBOOrganizationSite -Organization $org -URL $siteUrl -Recurse |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Save a certain SharePoint organization site URL address to the $siteUrl variable. 3. Run the Get-VBOrganizationSite cmdlet with the $org variable. Specify the $siteUrl variable as the URL parameter value to get an organization site with a specified URL. Use the Recurse parameter to also get all sub-levels child sites. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Only Child Sites

|  |  |
| --- | --- |
| This example shows how to get only one sub-level child site of the parent organization site $parentSite.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  $parentSite = "https://exampleorganization.sharepoint.com/sites/exampleparentsite"  Get-VBOOrganizationSite -Organization $org -ParentURL $parentSite |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Save a certain SharePoint organization site URL address to the $parentSite variable. 3. Run the Get-VBOrganizationSite cmdlet with the $org variable. Specify the $parentSite variable as the ParentURL parameter value to get one sub-level child site of the $parentSite organization site. |

Related Commands

[Get-VBOOrganization](get-vboorganization.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
