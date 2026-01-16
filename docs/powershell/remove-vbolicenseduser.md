---
title: "remove-vbolicenseduser"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vbolicenseduser.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Removes licenses from Veeam Backup for Microsoft 365 users.

|  |
| --- |
| ![Remove-VBOLicensedUser](images/icon_important.webp) Important |
| You must remove user data from the backup repository before removing a license from Veeam Backup for Microsoft 365 users. Run the [Remove-VBOEntityData](remove-vboentitydata.md) cmdlet to remove the user data. |

Syntax

|  |
| --- |
| Remove-VBOLicensedUser [-User <VBOLicensedUser>] [<CommonParameters>] |

Detailed Description

This cmdlet removes licenses from Veeam Backup for Microsoft 365 users.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| User | Specifies a licensed user. The cmdlet will remove license from this user. | Accepts the VBOLicensedUser object.  To get this object, run the [Get-VBOLicensedUser](get-vbolicenseduser.md) cmdlet. | True | 0 | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing Licensed Users from Veeam Backup for Microsoft 365 Server

This example shows how to remove a license from the John Smith licensed user from the Columbus organization.

|  |
| --- |
| $org = Get-VBOOrganization -Name "Columbus"  $licensedUser = Get-VBOLicensedUser -Organization $org -Name "John Smith"  Remove-VBOLicensedUser -User $licensedUser |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Specify the Name parameter value. Save the result to the $org variable.
2. Run the [Get-VBOLicensedUser](get-vbolicenseduser.md) cmdlet. Specify the Organization and Name parameters value. Save the result to the $licensedUser variable.
3. Run the Remove-VBOLicensedUser cmdlet. Set the $licensedUser variable as the User parameter value.

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOLicensedUser](get-vbolicenseduser.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
