---
title: "new-vbobackupaccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vbobackupaccount.html"
last_updated: "12/17/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Creates auxiliary backup accounts to back up SharePoint and OneDrive for Business.

Syntax

|  |
| --- |
| New-VBOBackupAccount -SecurityGroupMember <VBOOrganizationGroupMember> -Password <SecureString> [<CommonParameters>] |

Detailed Description

This cmdlet creates the VBOBackupAccount object that defines settings of auxiliary backup accounts.

|  |
| --- |
| ![New-VBOBackupAccount](images/icon_important.webp) Important |
| You cannot configure auxiliary backup accounts for on-premises Microsoft SharePoint organizations.  The entire security group will be granted the Site Collection Administrator role, which means that each user in this group will be granted this role as well, regardless of what users have been added with the SecurityGroupMember parameter. The role, however, can only be granted if you have used the GrantRolesAndPermissions parameter when defining connection settings to access the Microsoft 365 organization. Granting occurs during the first session of each of the backup jobs with SharePoint or OneDrive for Business items. If a user ceases to be a member of the group, the role is automatically annulled for this user. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| SecurityGroupMember | Specifies security groups. The cmdlet will use accounts from these security groups to back up Microsoft SharePoint and OneDrive for Business data. | Accepts the VBOOrganizationGroupMember object.  To get this object, run the [Get-VBOOrganizationGroupMember](get-vboorganizationgroupmember.md) cmdlet. | True | Named | False |
| Password | Specifies a password. The cmdlet will use this password to back up Microsoft SharePoint and OneDrive for Business data. | SecureString | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

This cmdlet returns the VBOBackupAccount object that defines settings of auxiliary backup accounts to back up Microsoft SharePoint and OneDrive for Business data

Example

Defining Auxiliary Backup Account to Back Up Microsoft SharePoint and OneDrive for Business

This example shows how to define auxiliary backup account to back up Microsoft SharePoint and OneDrive for Business.

|  |
| --- |
| $org = Get-VBOOrganization  $group = Get-VBOOrganizationGroup -Organization $org -DisplayName "VBOWorkGroup"  $members = Get-VBOOrganizationGroupMember -Group $group  $pwd = ConvertTo-SecureString -String "Pa$$word123" -AsPlainText -Force  New-VBOBackupAccount -SecurityGroupMember $members[0] -Password $pwd |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $org variable.
2. Run the [Get-VBOOrganizationGroup](get-vboorganizationgroup.md) cmdlet. Set the $org variable as the Organization parameter value. Specify the DisplayName parameter value. Save the result to the $group variable.
3. Run the [Get-VBOOrganizationGroupMember](get-vboorganizationgroupmember.md) cmdlet. Set the $group variable as the Group variable value. Save the result to the $members variable.
4. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet. Specify the necessary parameters. Save the result to the $pwd variable.
5. Run the New-VBOBackupAccount cmdlet. Set the $members variable as the SecurityGroupMember parameter value. Set the $pwd variable as the Password parameter value.

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationGroup](get-vboorganizationgroup.md)
* [Get-VBOOrganizationGroupMember](get-vboorganizationgroupmember.md)
* [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)

Page updated 12/17/2024

Page content applies to build 8.3.0.2201
