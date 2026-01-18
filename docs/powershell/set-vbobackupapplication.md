---
title: "Set-VBOBackupApplication"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbobackupapplication.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Set-VBOBackupApplication


Short Description

Modifies backup application settings that are added to Microsoft organizations.

Syntax

|  |
| --- |
| Set-VBOBackupApplication -BackupApplication <VBOBackupApplication> -ApplicationCertificatePath <String> [-ApplicationCertificatePassword <SecureString>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies backup application settings that are added to Microsoft organizations. The backup application represents settings of a Microsoft Entra application. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

|  |
| --- |
| ![Set-VBOBackupApplication](images/icon_important.webp) Important |
| This cmdlet will run only for Microsoft organizations that are added to the Veeam Backup for Microsoft 365 infrastructure using modern app-only authentication method. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| BackupApplication | Specifies a backup application whose settings you want to modify. | Accepts the [VBOBackupApplication](vbobackupapplication.md) object.  To get this object, run the [Get-VBOBackupApplication](get-vbobackupapplication.md) cmdlet. | True | Named | False |
| ApplicationCertificatePath | Specifies a path to the folder where the certificate is located. The cmdlet will modify the path to the certificate in the backup application settings. | String | True | Named | False |
| ApplicationCertificatePassword | Specifies the certificate password. The cmdlet will modify the password in the backup application settings. | SecureString | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOBackupApplication](vbobackupapplication.md) object that contains backup application settings that are added to Microsoft organizations.

Example

Modifying Backup Application Certificate Path and Password

This example shows how to modify a path to the folder where the certificate is located. The cmdlet will change it to the C:\NewCertificate\cert.pfx value.

|  |
| --- |
| $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  $app = Get-VBOBackupApplication  Set-VBOBackupApplication -BackupApplication $app -ApplicationCertificatePath "C:\NewCertificate\cert.pfx" -ApplicationCertificatePassword $securepassword |

Perform the following steps:

1. Specify the secure password.

1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable.
2. Enter the password.

1. Run the [Get-VBOBackupApplication](get-vbobackupapplication.md) cmdlet. Save the result to the $app variable.
2. Run the Set-VBOBackupApplication cmdlet. Specify the following settings:

* Set the $app variable as the BackupApplication parameter value.
* Specify the ApplicationCertificatePath parameter value.
* Set the $securepassword variable as the ApplicationCertificatePassword parameter value.

Related Commands

* [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)
* [Get-VBOBackupApplication](get-vbobackupapplication.md)


