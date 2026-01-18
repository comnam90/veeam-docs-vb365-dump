---
title: "New-VBOBackupApplication"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vbobackupapplication.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# New-VBOBackupApplication


Short Description

Defines backup application settings to back up SharePoint and OneDrive for Business.

Syntax

This cmdlet provides parameter sets that allow you to:

* Defines settings of an existing backup application.

|  |
| --- |
| New-VBOBackupApplication -Application <VBOApplication> -ApplicationCertificatePath <String> [-ApplicationCertificatePassword <SecureString>] [<CommonParameters>] |

* Define settings for a new backup application.

|  |
| --- |
| New-VBOBackupApplication -Name <String> -Organization <VBOOrganization> -ApplicationCertificatePath <String> [-ApplicationCertificatePassword <SecureString>] [-Count <Int32>] [<CommonParameters>] |

Detailed Description

This cmdlet creates the [VBOBackupApplication](vbobackupapplication.md) object that defines backup application settings. The backup application represents settings of a Microsoft Entra application.

|  |
| --- |
| ![New-VBOBackupApplication](images/icon_important.webp) Important |
| This cmdlet will run only for Microsoft organizations that are added to the Veeam Backup for Microsoft 365 infrastructure using modern app-only authentication method. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Application | Specifies a backup application. The cmdlet will modify the settings of this application. | Accepts the [VBOApplication](vboapplication.md) object.  To get this object, run the [Get-VBOApplication](get-vboapplication.md) cmdlet. | True | Named | False |
| ApplicationCertificatePath | Specifies a path to the folder where the certificate is located. The cmdlet will use this certificate to set a backup application. | String | True | Named | False |
| ApplicationCertificatePassword | Specifies the certificate password. The cmdlet will use this password to set a backup application. | SecureString | False | Named | False |
| Name | Specifies a name of the backup application. The cmdlet will set this name to the application. | String | True | Named | False |
| Organization | Specifies a Microsoft organization. The cmdlet will modify a backup application of this organization. | Accepts the [VBOOrganization](vboorganization.md) object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| Count | Specifies the number of backup applications. The cmdlet will create the specified number of applications. | Int32 | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOBackupApplication](vbobackupapplication.md) object that defines backup application settings.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Defining Settings of New Backup Application

|  |  |
| --- | --- |
| This example shows how to define settings of a new backup application.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  $org = Get-VBOOrganization  $app = Get-VBOApplication -Organization $org  New-VBOBackupApplication -Application $app -ApplicationCertificatePath "C:\certificate\cert.pfx" -ApplicationCertificatePassword $securepassword |  Perform the following steps:   1. Specify the secure password:  1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password.  1. Get an application:  1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $org variable. 2. Run the [Get-VBOApplication](get-vboapplication.md) cmdlet. Set the $org variable as the Organization parameter value.  1. Run the New-VBOBackupApplication cmdlet. Specify the following settings:  * Set the $app variable as the Application parameter value. * Specify the ApplicationCertificatePath parameter value. * Set the $securepassword variable as the ApplicationCertificatePassword parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Defining Settings of Existing Backup Application

|  |  |
| --- | --- |
| This example shows how to define settings of an existing backup application.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  $org = Get-VBOOrganization  New-VBOBackupApplication -Name "BackupApp09" -Organization $org -ApplicationCertificatePath "C:\certificate\cert.pfx" -ApplicationCertificatePassword $securepassword |  Perform the following steps:   1. Specify the secure password:  1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password.  1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $org variable. 2. Run the New-VBOBackupApplication cmdlet. Specify the following settings:  * Specify the Name parameter value. * Set the $org variable as the Organization parameter value. * Specify the ApplicationCertificatePath parameter value. * Specify the ApplicationCertificatePassword parameter value. |

Related Commands

* [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)
* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOApplication](get-vboapplication.md)


