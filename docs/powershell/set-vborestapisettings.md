---
title: "set-vborestapisettings"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vborestapisettings.html"
last_updated: "5/30/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies REST API settings.

Syntax

|  |
| --- |
| Set-VBORestAPISettings [-EnableService] [-AuthTokenLifeTime <Int32>] [-HTTPSPort <Int32>] [-CertificateFilePath <String>] [-CertificatePassword <SecureString>] [-EnableSwaggerUI] [-EnableOperatorAuthenticationOnly] [<CommonParameters>] |

Detailed Description

This cmdlet modifies REST API settings that are used by Veeam Backup for Microsoft 365 REST API Service. For SSL connections, Veeam Backup for Microsoft 365 REST API uses SSL certificate.

To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

|  |
| --- |
| ![Set-VBORestAPISettings](images/icon_note.webp) Note |
| This cmdlet accepts the SecureString type. Use Microsoft PowerShell standard capabilities to convert your password into the SecureString. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| EnableService | Defines that the cmdlet will start Veeam Backup for Microsoft 365 REST API Service.  Default: False | SwitchParameter | False | Named | False |
| AuthTokenLifeTime | Specifies the lifetime value for the authentication token (minutes).  Default: 60 | Int32 | False | Named | False |
| HTTPSPort | Specifies a port number for server-client communication over HTTPS protocol.  Default: 4443 | Int32 | False | Named | False |
| CertificateFilePath | Specifies a path to the SSL certificate file. | String | False | Named | False |
| CertificatePassword | Specifies a password for the SSL certificate. | SecureString | False | Named | False |
| EnableSwaggerUI | Defines that the cmdlet will enable access to the swagger website and usage of Swagger UI.  Default: False | SwitchParameter | False | Named | False |
| EnableOperatorAuthenticationOnly | Defines that Veeam Backup for Microsoft 365 will use REST API only for authentication of restore operators to Restore Portal.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Modifying REST API Settings

This example shows how to modify REST API settings:

* Set authentication token lifetime to 4800 minutes.
* Locate the SSL certificate file and specify the certificate password.

|  |
| --- |
| $plainpassword = "Password1234plain"  $securepassword = $plainpassword | ConvertTo-SecureString -AsPlainText -Force  Set-VBORestAPISettings -EnableService -AuthTokenLifeTime 4800 -CertificateFilePath "C:\Certificates" -CertificatePassword $securepassword |

Perform the following steps:

1. Assign your certificate password to the $plainpassword variable.
2. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet with the $plainpassword variable to turn the password into the SecureString type. Save the result to the $securepassword variable.
3. Run the Set-VBORestAPISettings cmdlet. Specify the following settings:

* Provide the EnableService parameter.
* Specify the AuthTokenLifeTime parameter value.
* Specify the CertificateFilePath parameter value.
* Set the $securepassword variable as the CertificatePassword parameter value.

Related Commands

[ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)

Page updated 5/30/2024

Page content applies to build 8.3.0.2201
