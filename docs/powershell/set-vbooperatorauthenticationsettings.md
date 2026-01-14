---
title: "set-vbooperatorauthenticationsettings"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbooperatorauthenticationsettings.html"
last_updated: "5/7/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies restore operator authentication settings.

Syntax

|  |
| --- |
| Set-VBOOperatorAuthenticationSettings [-EnableAuthentication] [-CertificateFilePath <String>] [-CertificatePassword <SecureString>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies restore operator authentication settings. These settings specify whether restore operators are allowed to authenticate to the Veeam Backup for Microsoft 365 server with Microsoft 365 credentials and an SSL certificate used to establish connection with the Veeam Backup for Microsoft 365 server.

To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

|  |
| --- |
| ![Set-VBOOperatorAuthenticationSettings](images/icon_note.webp) Note |
| This cmdlet accepts the SecureString type. Use Microsoft PowerShell standard capabilities to convert your password into the SecureString. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| EnableAuthentication | Defines that the cmdlet will enable restore operator authentication to the Veeam Backup for Microsoft 365 server with Microsoft 365 credentials.  Default: False | SwitchParameter | False | Named | False |
| CertificateFilePath | Specifies a path to the SSL certificate file. | String | False | Named | False |
| CertificatePassword | Specifies a password for the SSL certificate. | SecureString | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Installing New SSL Certificate to Authenticate Restore Operators

This example shows how to modify restore operator authentication settings, that is, install a new SSL certificate to be used by restore operators to establish connection with the Veeam Backup for Microsoft 365 server.

|  |
| --- |
| $plainpassword = "Password1234plain"  $securepassword = $plainpassword | ConvertTo-SecureString -AsPlainText -Force  Set-VBOOperatorAuthenticationSettings -EnableAuthentication -CertificateFilePath "C:\cert.pfx" -CertificatePassword $securepassword |

Perform the following steps:

1. Assign your certificate password to the $plainpassword variable.
2. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet with the $plainpassword variable to set the password to the SecureString type. Save the result to the $securepassword variable.
3. Run the Set-VBOOperatorAuthenticationSettings cmdlet. Specify the following settings:

* Provide the EnableAuthentication parameter.
* Specify the CertificateFilePath parameter value.
* Set the $securepassword variable as the CertificatePassword parameter value.

Related Commands

[ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)

Page updated 5/7/2024

Page content applies to build 8.3.0.2201
