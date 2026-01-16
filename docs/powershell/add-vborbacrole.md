---
title: "add-vborbacrole"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vborbacrole.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Adds a restore operator role to Veeam Backup for Microsoft 365.

Syntax

This cmdlet provides parameter sets that allow you to:

* Create a restore operator role to manage selected objects.

|  |
| --- |
| Add-VBORbacRole -Organization <VBOOrganization> -Name <String> [-Description <String>] -Operators <VBORbacOperator[]> -SelectedItems <VBORbacRoleItem[]> [-ExcludedItems <VBORbacRoleItem[]>] [<CommonParameters>] |

* Create a restore operator role to manage entire organization.

|  |
| --- |
| Add-VBORbacRole -Organization <VBOOrganization> -Name <String> [-Description <String>] -Operators <VBORbacOperator[]> [-EntireOrganization] [-ExcludedItems <VBORbacRoleItem[]>] [<CommonParameters>] |

Detailed Description

This cmdlet adds a restore operator role to Veeam Backup for Microsoft 365. When you add a restore operator role, you assign permissions to restore operators to explore and restore data from backups created by Veeam Backup for Microsoft 365 for specific organization object types (users, groups, sites, teams, or the entire Microsoft 365 organization).

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will add a restore operator role to the specified Microsoft organization.  Note: The organization must be a Microsoft 365 organization with modern app-only authentication or hybrid organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| Name | Specifies a restore operator role name. The cmdlet will add a restore operator role with this name. | String | True | Named | False |
| Description | Specifies a description of the restore operator role. | String | False | Named | False |
| Operators | Specifies an array of restore operators. The cmdlet will assign permissions to these objects. | Accepts the VBORbacOperator[] object.  To create this object, run the [New-VBORbacOperator](new-vborbacoperator.md) cmdlet. | True | Named | False |
| SelectedItems | Specifies an array of objects to manage. The cmdlet will add a restore operator role in which the specified restore operators are allowed to explore and restore backed-up data of these objects. | Accepts the VBORbacRoleItem[] object.  To create this object, run the [New-VBORbacRoleItem](new-vborbacroleitem.md) cmdlet. | True | Named | False |
| ExcludedItems | Specifies an array of objects to exclude. The cmdlet will add a restore operator role in which the specified restore operators are not allowed to explore and restore backed-up data of these objects.  Note: You cannot exclude objects that have been specified for the SelectedItems parameter. | Accepts the VBORbacRoleItem[] object.  To create this object, run the [New-VBORbacRoleItem](new-vborbacroleitem.md) cmdlet. | False | Named | False |
| EntireOrganization | Defines that the specified restore operators will be able to explore and restore all objects within the specified Microsoft 365 organization.  Default: False | SwitchParameter | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBORbacRole object that contains the restore operator role settings.

Example

Adding Restore Operator Role to Microsoft Organization

This example shows how add a restore operator role:

* Define an organization group with the display name UsersAlpha as a restore operator of the organization with the name ABC.
* Define all organization users with a name starting with A as objects to manage.
* Define all organization users with a name starting with B as objects to exclude.

|  |
| --- |
| $org = Get-VBOOrganization -Name "ABC"  $Group = Get-VBOOrganizationGroup -Organization $org -DisplayName "UsersAlpha"  $restoreoperator = New-VBORbacOperator -Group $Group  $UserA = Get-VBOOrganizationUser -Organization $org -DisplayName "A\*"  $selecteditems = New-VBORbacRoleItem -User $UserA  $UserB = Get-VBOOrganizationUser -Organization $org -DisplayName "B\*"  $excludeditems = New-VBORbacRoleItem -User $UserB  Add-VBORbacRole -Organization $org -Name "ABC Restore Operators" -Operators $restoreoperator -SelectedItems $selecteditems -ExcludedItems $excludeditems |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable.
2. Run the [Get-VBOOrganizationGroup](get-vboorganizationgroup.md) cmdlet with the $org variable and the DisplayName parameter to get an organization group with the display name UsersAlpha. Save the result to the $Group variable.
3. Run the [New-VBORbacOperator](new-vborbacoperator.md) cmdlet. Set the $Group variable as the Group parameter value. Save the result to the $restoreoperator variable.
4. Run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet with the $org variable and the A\* value for the DisplayName parameter to get all organization users with a name starting with A. Save the result to the $UserA variable.
5. Run the [New-VBORbacRoleItem](new-vborbacroleitem.md) cmdlet. Set the $UserA variable as the User parameter value. Save the result to the $selecteditems variable.
6. Run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet with the $org variable and the B\* value for the DisplayName parameter to get all organization users with a name starting with B. Save the result to the $UserB variable.
7. Run the [New-VBORbacRoleItem](new-vborbacroleitem.md) cmdlet. Set the $UserB variable as the User parameter value. Save the result to the $excludeditems variable.
8. Run the Add-VBORbacRole cmdlet. Specify the following settings:

* Set the $org variable as the Organization parameter value.
* Specify the Name parameter value.
* Set the $restoreoperator variable as the Operators parameter value.
* Set the $selecteditems variable as the SelectedItems parameter value.
* Set the $excludeditems variable as the ExcludedItems parameter value.

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationGroup](get-vboorganizationgroup.md)
* [Get-VBOOrganizationUser](get-vboorganizationuser.md)
* [New-VBORbacOperator](new-vborbacoperator.md)
* [New-VBORbacRoleItem](new-vborbacroleitem.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
