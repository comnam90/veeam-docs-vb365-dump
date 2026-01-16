---
title: "new-vborbacoperator"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vborbacoperator.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Defines users or groups that will act as restore operators.

Syntax

This cmdlet provides parameter sets that allow you to:

* Create restore operators that represent users.

|  |
| --- |
| New-VBORbacOperator -User <VBOOrganizationUser[]> [<CommonParameters>] |

* Create restore operators that represent groups.

|  |
| --- |
| New-VBORbacOperator -Group <VBOOrganizationGroup[]> [<CommonParameters>] |

Detailed Description

This cmdlet creates the VBORbacOperator object. This object contains users or groups that will act as restore operators.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| User | Specifies an array of users added to Veeam Backup for Microsoft 365. The cmdlet will define these users as restore operators. | Accepts the VBOOrganizationUser[] object.  To get this object, run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet. | True | Named | False |
| Group | Specifies an array of groups added to Veeam Backup for Microsoft 365. The cmdlet will define these groups as restore operators. | Accepts the VBOOrganizationGroup[] object.  To get this object, run the [Get-VBOOrganizationGroup](get-vboorganizationgroup.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBORbacOperator object that contains details on users or groups that will act as restore operators.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Defining User as Restore Operator

|  |  |
| --- | --- |
| This example shows how to define the userAlpha@tech.onmicrosoft.com organization user as a restore operator of the organization with the name ABC.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  $User = Get-VBOOrganizationUser -Organization $org -UserName "userAlpha@tech.onmicrosoft.com"  New-VBORbacOperator -User $User |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet with the $org variable and the userAlpha@tech.onmicrosoft.com value for the UserName parameter to get an organization user with the name userAlpha. Save the result to the $User variable. 3. Run the New-VBORbacOperator cmdlet. Set the $User variable as the User parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Defining Group as Restore Operator

|  |  |
| --- | --- |
| This example shows how to define an organization group with the display name UsersAlpha as a restore operator of the organization with the name ABC.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  $Group = Get-VBOOrganizationGroup -Organization $org -DisplayName "UsersAlpha"  New-VBORbacOperator -Group $Group |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the [Get-VBOOrganizationGroup](get-vboorganizationgroup.md) cmdlet with the $org variable and the DisplayName parameter to get an organization group with the display name UsersAlpha. Save the result to the $Group variable. 3. Run the New-VBORbacOperator cmdlet. Set the $Group variable as the Group parameter value. |

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationUser](get-vboorganizationuser.md)
* [Get-VBOOrganizationGroup](get-vboorganizationgroup.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
