---
title: "Set-VBORbacRole"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vborbacrole.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# Set-VBORbacRole


Short Description

Modifies settings of restore operator roles that are added to Veeam Backup for Microsoft 365.

Syntax

This cmdlet provides parameter sets that allow you to:

* Modify settings of the restore operator role that allows you to manage selected objects.

|  |
| --- |
| Set-VBORbacRole -Role <VBOOperatorRole> [-Name <String>] [-Description <String>] [-Operators <VBORbacOperator[]>] [-SelectedItems <VBORbacRoleItem[]>] [-ExcludedItems <VBORbacRoleItem[]>] [<CommonParameters>] |

* Modify settings of the restore operator role that allows you to manage entire organization.

|  |
| --- |
| Set-VBORbacRole -Role <VBOOperatorRole> [-Name <String>] [-Description <String>] [-Operators <VBORbacOperator[]>] [-EntireOrganization] [-ExcludedItems <VBORbacRoleItem[]>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies settings of the specified restore operator role. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Role | Specifies a restore operator role.  The cmdlet will modify settings of this restore operator role. | Accepts the [VBOOperatorRole](vbooperatorrole.md) object.  To get this object, run the [Get-VBORbacRole](get-vborbacrole.md) cmdlet. | True | Named | True (ByValue) |
| Name | Specifies a restore operator role name. The cmdlet will replace the current name with the specified name. | String | False | Named | False |
| Description | Specifies a description of the restore operator role. The cmdlet will replace the current description with the specified description. | String | False | Named | False |
| Operators | Specifies an array of restore operators. The cmdlet will replace the current restore operators with the specified restore operators. | Accepts the [VBORbacOperator](vborbacoperator.md)[] object.  To create this object, run the [New-VBORbacOperator](new-vborbacoperator.md) cmdlet. | False | Named | False |
| SelectedItems | Specifies an array of objects to manage. The cmdlet will replace the current objects to manage with the specified ones. | Accepts the [VBORbacRoleItem](vborbacroleitem.md)[] object.  To create this object, run the [New-VBORbacRoleItem](new-vborbacroleitem.md) cmdlet. | False | Named | False |
| ExcludedItems | Specifies an array of objects to exclude. The cmdlet will replace the current objects to exclude with the specified ones.  Note: You cannot exclude objects that have been specified for the SelectedItems parameter. | Accepts the [VBORbacRoleItem](vborbacroleitem.md)[] object.  To create this object, run the [New-VBORbacRoleItem](new-vborbacroleitem.md) cmdlet. | False | Named | False |
| EntireOrganization | Defines that the specified restore operators will be able to explore and restore all objects within the specified Microsoft 365 organization.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOOperatorRole](vbooperatorrole.md) object that contains the restore operator role settings.

Example

Modifying Restore Operators List

This example shows how to change a list of restore operators added to the specified restore operator role.

|  |
| --- |
| $org = Get-VBOOrganization -Name "ABC"  $role = Get-VBORbacRole -Name "ABC Restore Operators"  $User = Get-VBOOrganizationUser -Organization $org -UserName "userAlpha@tech.onmicrosoft.com"  $newrestoreoperator = New-VBORbacOperator -User $User  Set-VBORbacRole -Role $role -Operators $newrestoreoperator |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable.
2. Run the [Get-VBORbacRole](get-vborbacrole.md) cmdlet with the Name parameter to get the restore operator role whose settings you want to modify. Save the result to the $role variable.
3. Run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet with the $org variable and the userAlpha@tech.onmicrosoft.com value for the UserName parameter to get an organization user with the name userAlpha. Save the result to the $User variable.
4. Run the [New-VBORbacOperator](new-vborbacoperator.md) cmdlet. Set the $User variable as the User parameter value. Save the result to the $newrestoreoperator variable.
5. Run the Set-VBORbacRole cmdlet. Set the $role variable as the Role parameter value and the $newrestoreoperator variable as the Operators parameter value.

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBORbacRole](get-vborbacrole.md)
* [Get-VBOOrganizationUser](get-vboorganizationuser.md)
* [New-VBORbacOperator](new-vborbacoperator.md)
* [New-VBORbacRoleItem](new-vborbacroleitem.md)


