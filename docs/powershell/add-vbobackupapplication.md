---
title: "add-vbobackupapplication"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vbobackupapplication.html"
last_updated: "6/5/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Adds backup application settings to an application pool.

Syntax

|  |
| --- |
| Add-VBOBackupApplication -Organization <VBOOrganization> -BackupApplications <VBOBackupApplication[]> [<CommonParameters>] |

Detailed Description

This cmdlet adds backup application settings to an application pool.

|  |
| --- |
| ![Add-VBOBackupApplication](images/icon_important.webp) Important |
| This cmdlet will run only for Microsoft organizations that are added to the Veeam Backup for Microsoft 365 infrastructure using modern app-only authentication method. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will add backup application settings to the specified Microsoft organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| BackupApplications | Specifies an array of backup applications. The cmdlet will add these backup applications to the Microsoft organization. | Accepts the VBOBackupApplication[] object.  To create this object, run the [New-VBOBackupApplication](new-vbobackupapplication.md) cmdlet. | True | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOBackupApplication object that contains backup application settings that are added to Microsoft organizations.

Example

Adding Backup Application to Microsoft Organization

This example shows how to add a backup application to an application pool of Microsoft organization.

|  |
| --- |
| $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  $org = Get-VBOOrganization  $app = Get-VBOApplication -Organization $org -Name "New\_App"  $newApp = New-VBOBackupApplication -Application $app -ApplicationCertificatePath "C:\certificate\cert.pfx" -ApplicationCertificatePassword $securepassword  Add-VBOBackupApplication -Organization $org -BackupApplications $newApp |

Perform the following steps:

1. Specify the secure password:

1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable.
2. Enter the password.

1. Get an application:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $org variable.
2. Run the [Get-VBOApplication](get-vboapplication.md) cmdlet. Set the $org variable as the Organization parameter value. Specify the Name parameter value. Save the result to the $app variable.

1. Run the [New-VBOBackupApplication](new-vbobackupapplication.md) cmdlet. Specify the Application, ApplicationCertificatePath and ApplicationCertificatePassword parameters. Save the result to the $newApp variable.
2. Run the Add-VBOBackupApplication cmdlet. Set the $org variable as the Organization parameter value. Set the $newApp variable as the BackupApplications parameter value.

Related Commands

* [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)
* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOApplication](get-vboapplication.md)
* [New-VBOBackupApplication](new-vbobackupapplication.md)

Page updated 6/5/2025

Page content applies to build 8.3.0.2201
