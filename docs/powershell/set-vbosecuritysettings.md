---
title: "Set-VBOSecuritySettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbosecuritysettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Set-VBOSecuritySettings


Short Description

Modifies security settings.

Syntax

|  |
| --- |
| Set-VBOSecuritySettings -CertificateFilePath <String> [-CertificatePassword <SecureString>] [-Force] [<CommonParameters>] |

Detailed Description

This cmdlet modifies security settings. These settings specify an SSL certificate used to establish connection with backup proxy servers in a workgroup.

To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

|  |
| --- |
| ![Set-VBOSecuritySettings](images/icon_note.webp) Note |
| This cmdlet accepts the SecureString type. Use Microsoft PowerShell standard capabilities to convert your password into the SecureString. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| CertificateFilePath | Specifies a path to the SSL certificate file. | String | True | Named | False |
| CertificatePassword | Specifies a password for the SSL certificate. | SecureString | False | Named | False |
| Force | Defines that the cmdlet will change security settings without prompting the user to confirm the operation.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOSecuritySettings](vbosecuritysettings.md) object that contains security settings.

Example

Installing New SSL Certificate

This example shows how to modify security settings, that is, install a new SSL certificate to be used by workgroup backup proxy servers.

|  |
| --- |
| $plainpassword = "Password1234plain"  $securepassword = $plainpassword | ConvertTo-SecureString -AsPlainText -Force  Set-VBOSecuritySettings -CertificateFilePath "C:\Certificates" -CertificatePassword $securepassword -Force |

Perform the following steps:

1. Assign your certificate password to the $plainpassword variable.
2. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet with the $plainpassword variable to set the password to the SecureString type. Save the result to the $securepassword variable.
3. Run the Set-VBOSecuritySettings cmdlet with the $securepassword variable. Specify the CertificateFilePath parameter value. Provide the Force parameter.

Related Commands

[ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)


