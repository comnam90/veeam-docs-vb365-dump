---
title: "get-vboorganizationgroupmember"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboorganizationgroupmember.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns members of organization groups.

Syntax

|  |
| --- |
| Get-VBOOrganizationGroupMember -Group <VBOOrganizationGroup> [-DataSource <VBOOrganizationDataSource>] [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of members added to organization groups.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Group | Specifies an organization group. The cmdlet will return members added to this group. | Accepts the VBOOrganizationGroup object.  To get this object, run the [Get-VBOOrganizationGroup](get-vboorganizationgroup.md) cmdlet. | True | Named | True (ByValue) |
| DataSource | Specifies how the cmdlet will return members of organization groups:   * PreferLocal   For Microsoft organizations with modern app-only authentication, the cmdlet will return data from either the organization cache database if organization objects are already synchronized to this source, or directly from the organization if synchronization is in progress.  For Microsoft organizations with modern authentication and legacy protocols or with basic authentication, the cmdlet will return data directly from the organization.   * Production   The cmdlet will return data directly from the organization.   * PreferLocalResynced   For Microsoft organizations with modern app-only authentication, the cmdlet will start synchronization of objects with the organization cache database and upon synchronization completes, it returns data from the organization cache database.  For Microsoft organizations with modern authentication and legacy protocols or with basic authentication, the cmdlet will return data directly from the organization.  Default: PreferLocal | VBOOrganizationDataSource | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

This cmdlet returns the VBOOrganizationGroupMember object that contains an array of members added to organization groups.

Example

Getting Organization Group Members

This example shows how to get organization group members added to organization groups.

|  |
| --- |
| $organization = Get-VBOOrganization  $group = Get-VBOOrganizationGroup -Organization $organization -DisplayName "Exchange Group"  Get-VBOOrganizationGroupMember -Group $group |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $organization variable.
2. Run the [Get-VBOOrganizationGroup](get-vboorganizationgroup.md) cmdlet. Set the $organization variable as the Organization parameter value. Specify the DisplayName parameter value. Save the result to the $group variable.
3. Run the Get-VBOOrganizationGroupMember cmdlet. Set the $group variable as the Group parameter value.

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationGroup](get-vboorganizationgroup.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
