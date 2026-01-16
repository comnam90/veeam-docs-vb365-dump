---
title: "set-vborestoreportalsettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vborestoreportalsettings.html"
last_updated: "8/15/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies connection settings to access Restore Portal.

Syntax

|  |
| --- |
| Set-VBORestorePortalSettings [-EnableService] [-ApplicationId <Guid>] [-CertificateFilePath <String>] [-Region <VBOOffice365Region>] [-CertificatePassword <SecureString>] [-PortalUri <String>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies connection settings to access Restore Portal. These settings specify whether Restore Portal is enabled, an identification number of Microsoft Entra application configured to access Restore Portal and an SSL certificate used for data exchange.

To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

|  |
| --- |
| ![Set-VBORestorePortalSettings](images/icon_note.webp) Note |
| This cmdlet accepts the SecureString type. Use Microsoft PowerShell standard capabilities to convert your password into the SecureString. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| EnableService | Defines that the cmdlet will enable Restore Portal.  Default: False | SwitchParameter | False | Named | False |
| ApplicationId | Specifies Microsoft Entra application ID. The cmdlet will use an application with this ID to connect to Restore Portal. | Guid | False | Named | False |
| CertificateFilePath | Specifies a path to the SSL certificate file. | String | False | Named | False |
| Region | Specifies Microsoft Entra region where Microsoft 365 organization datacenter is located:   * China * Germany * USDefence * USGovernment * Worldwide | VBOOffice365Region | False | Named | False |
| CertificatePassword | Specifies a password for the SSL certificate. | SecureString | False | Named | False |
| PortalUri | Specifies web address of a machine with the Veeam Backup for Microsoft 365 REST API component installed.  Before you add URI, consider the following restrictions:   * The website is available over HTTPS protocol only. * By default, port 4443 must be opened on the Veeam Backup for Microsoft 365 server or a machine with the Veeam Backup for Microsoft 365 REST API component installed. * The web address must be specified in one of the following formats:  * https://<IPv4 address>:<port number>, where <IPv4 address> is a public IPv4 address of a machine with the Veeam Backup for Microsoft 365 REST API component installed.  * https://<DNS hostname>:<port number>, where <DNS hostname> is DNS hostname of a machine with the Veeam Backup for Microsoft 365 REST API component installed. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Modifying Authentication Settings to Access Restore Portal

This example shows how to modify connection settings to access Restore Portal:

* Change identification number of Microsoft Entra application.
* Locate the SSL certificate file and specify the certificate password.
* Specify web address to open Restore Portal in a web browser window.

|  |
| --- |
| $plainpassword = "Password1234plain"  $securepassword = $plainpassword | ConvertTo-SecureString -AsPlainText -Force  Set-VBORestorePortalSettings -EnableService -ApplicationId 98ce1588-597b-4e24-be7c-8a7f9fda41d4 -CertificateFilePath "C:\Certificates" -CertificatePassword $securepassword -PortalUri "https://portal.abc.com:4443" |

Perform the following steps:

1. Assign the certificate password to the $plainpassword variable.
2. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet with the $plainpassword variable to turn the password into the SecureString type. Save the result to the $securepassword variable.
3. Run the Set-VBORestorePortalSettings cmdlet. Specify the following settings:

* Provide the EnableService parameter.
* Specify the ApplicationId parameter value.
* Specify the CertificateFilePath parameter value.
* Set the $securepassword variable as the CertificatePassword parameter value.
* Specify the PortalUri parameter value.

Related Commands

[ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)

Page updated 8/15/2024

Page content applies to build 8.3.0.2201
