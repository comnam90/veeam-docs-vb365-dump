---
title: "Set-VBOTenantAuthenticationSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbotenantauthenticationsettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Set-VBOTenantAuthenticationSettings


Short Description

Modifies the Veeam Backup for Microsoft 365 tenant authentication settings.

Syntax

|  |
| --- |
| Set-VBOTenantAuthenticationSettings [-EnableAuthentication] [-CertificateFilePath <String>] [-CertificatePassword <SecureString>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies tenant authentication settings configured for Veeam Backup for Microsoft 365. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

|  |
| --- |
| ![Set-VBOTenantAuthenticationSettings](images/icon_note.webp) Note |
| This cmdlet accepts the SecureString type. Use Microsoft PowerShell standard capabilities to convert your password into the SecureString. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| EnableAuthentication | Defines that the cmdlet will enable tenant authentication to the Veeam Backup for Microsoft 365 server with organization credentials.  Default: False | SwitchParameter | False | Named | False |
| CertificateFilePath | Specifies a path to the tenant authentication certificate file. | String | False | Named | False |
| CertificatePassword | Specifies a password for the tenant authentication certificate. | SecureString | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOTenantAuthenticationSettings](vbotenantauthenticationsettings.md) object that contains the Veeam Backup for Microsoft 365 tenant authentication settings.

Example

Modifying Tenant Authentication Settings

This example shows how to modify tenant authentication settings.

|  |
| --- |
| $plainpassword = "Password1234plain"  $securepassword = $plainpassword | ConvertTo-SecureString -AsPlainText -Force  Set-VBOTenantAuthenticationSettings -EnableAuthentication -CertificateFilePath "C:\cert.pfx" -CertificatePassword $securepassword |

Perform the following steps:

1. Assign your certificate password to the $plainpassword variable.
2. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet with the $plainpassword variable to turn the password into the SecureString type. Save the result to the $securepassword variable.
3. Run the Set-VBOTenantAuthenticationSettings cmdlet with the $securepassword variable and EnableAuthentication parameter.

Related Commands

[ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)


