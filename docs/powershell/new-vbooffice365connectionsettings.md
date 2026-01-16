---
title: "new-vbooffice365connectionsettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vbooffice365connectionsettings.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Defines connection settings to access Microsoft 365 organizations.

Syntax

This cmdlet provides parameter sets that allow you to:

* Define connection settings to access Microsoft 365 organizations using basic authentication.

|  |
| --- |
| New-VBOOffice365ConnectionSettings -Credential <PSCredential> [-GrantRolesAndPermissions] [-VeeamAADApplicationUsed] [<CommonParameters>] |

* Define connection settings to access Microsoft 365 organizations using modern authentication with legacy protocols allowed by specifying an application secret.

|  |
| --- |
| New-VBOOffice365ConnectionSettings -AppCredential <PSCredential> [-GrantRolesAndPermissions] -ApplicationId <Guid> -ApplicationSecret <SecureString> [<CommonParameters>] |

* Define connection settings to access Microsoft 365 organizations using modern authentication with legacy protocols allowed by specifying an application certificate.

|  |
| --- |
| New-VBOOffice365ConnectionSettings -AppCredential <PSCredential> [-GrantRolesAndPermissions] -ApplicationId <Guid> -ApplicationCertificatePath <String> [-ApplicationCertificatePassword <SecureString>] [<CommonParameters>] |

Deprecated Cmdlet Set

The following cmdlet set is deprecated. It still works in Veeam Backup for Microsoft 365 version 8 but may not be supported in the next versions of Veeam Backup for Microsoft 365.

|  |
| --- |
| New-VBOOffice365ConnectionSettings -Credential <PSCredential> [-GrantRolesAndPermissions] [-VeeamAADApplicationUsed] [<CommonParameters>] |

Detailed Description

This cmdlet creates the VBOOffice365LegacyConnectionSettings object. This object defines connection settings to access Microsoft 365 organizations. You can apply these settings to add Microsoft 365 organizations to the Veeam Backup for Microsoft 365 infrastructure.

Run the [Add-VBOOrganization](add-vboorganization.md) cmdlet to add Microsoft organizations to the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| ![New-VBOOffice365ConnectionSettings](images/icon_important.webp) Important |
| This type of connection settings utilizes legacy authentication protocols. Since [Microsoft deprecated basic authentication and legacy authentication protocols](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-september/ba-p/3609437), these authentication methods will be deprecated in future versions of Veeam Backup for Microsoft 365. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Credential | Note: This parameter is deprecated.  Specifies credentials. The cmdlet will use these credentials to connect to a Microsoft 365 organization. | PSCredential | True | Named | False |
| GrantRolesAndPermissions | Defines that the cmdlet will grant required permissions and assign appropriate roles to the account.  Default: False | SwitchParameter | False | Named | False |
| VeeamAADApplicationUsed | Defines that the cmdlet will use the Veeam application to connect to Microsoft Graph.  Note: You must set this parameter to true for the following Microsoft Entra regions:   * China * Germany   Default: False | SwitchParameter | False | Named | False |
| AppCredential | For the modern authentication type.  Specifies credentials. The cmdlet will use these credentials to connect to a Microsoft 365 organization. | PSCredential | True | Named | False |
| ApplicationId | For the modern authentication type.  Specifies an application ID. The cmdlet will use an application ID to connect to a Microsoft 365 organization. | Guid | True | Named | False |
| ApplicationSecret | For the modern authentication type.  Specifies an application secret. The cmdlet will use an application secret to connect to a Microsoft 365 organization. | SecureString | True | Named | False |
| ApplicationCertificatePath | For the modern authentication type.  Specifies a path to the application certificate. The cmdlet will use this path to get the application certificate and to connect to a Microsoft 365 organization. | String | True | Named | False |
| ApplicationCertificatePassword | For the modern authentication type.  Specifies the certificate password. The cmdlet will use these credentials to connect to a Microsoft 365 organization. | SecureString | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOOffice365LegacyConnectionSettings object that contains connection settings to access Microsoft 365 organizations.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Defining Connection Settings with Basic Authentication

|  |  |
| --- | --- |
| This example shows how to define Microsoft 365 organization connection settings with the basic authentication.  |  | | --- | | $credentials = Get-Credential  New-VBOOffice365ConnectionSettings -Credential $credentials -GrantRolesAndPermissions |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet to create a credential object. Enter credentials you want to use for authenticating to a Microsoft 365 organization. Save the result to the $credentials variable. 2. Run the New-VBOOffice365ConnectionSettings cmdlet. Set the $credentials variable as the Credential parameter value. Provide the GrantRolesAndPermissions parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Defining Connection Settings with Modern Authentication Using Application Secret

|  |  |
| --- | --- |
| This example shows how to define Microsoft 365 organization connection settings with a modern authentication using an application secret.  |  | | --- | | $Credentials = Get-Credential  $ApplicationSecret = ConvertTo-SecureString -String "fCblKbIf+kY10+uB+rROD+wZPT/WxcDNX+EU2O33Q1s=" -AsPlainText -Force  New-VBOOffice365ConnectionSettings -AppCredential $Credentials -ApplicationId d052f06e-1cfa-42ff-9636-9da5e7aa1fd -ApplicationSecret $ApplicationSecret -GrantRolesAndPermissions |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmldet to create a credential object. Enter credentials you want to use for authenticating to a Microsoft 365 organization. Save the result to the $Credentials variable. 2. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet to convert the plain text to the secure string. Specify the String parameter value. Provide the AsPlainText parameter to turn the plain text to the secure string. Provide the Force parameter. Save the result to the $ApplicationSecret variable. 3. Run the New-VBOOffice365ConnectionSettings cmdlet. Specify the following settings:  * Set the $Credentials variable as the AppCredential parameter value. * Specify the ApplicationId parameter value. * Set the $ApplicationSecret variable as ApplicationSecret parameter value. * Provide the GrantRolesAndPermissions parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Defining Connection Settings with Modern Authentication Using Application Certificate

|  |  |
| --- | --- |
| This example shows how to define Microsoft 365 organization connection settings with a modern authentication using an application certificate.  |  | | --- | | $Credentials = Get-Credential  $ApplicationCertificatePassword = ConvertTo-SecureString -String "fCblKbIf+kY10+uB+rROD+wZPT/WxcDNX+EU2O33Q1s=" -AsPlainText -Force  New-VBOOffice365ConnectionSettings -AppCredential $Credentials -ApplicationId d052f06e-1cfa-42ff-9636-9da5e7aa1fd1 -ApplicationCertificatePath "C:\ApplicationCertificate.pfx" -ApplicationCertificatePassword $ApplicationCertificatePassword -GrantRolesAndPermissions |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmldet to create a credential object. Enter credentials you want to use for authenticating to a Microsoft 365 organization. Save the result to the $Credentials variable. 2. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet to convert the plain text to the secure string. Specify the String parameter value. Provide the AsPlainText parameter to turn the plain text to the secure string. Provide the Force parameter. Save the result to the $ApplicationSecret variable. 3. Run the New-VBOOffice365ConnectionSettings cmdlet. Specify the following settings:  * Set the $Credentials variable as the AppCredential parameter value. * Specify the ApplicationId parameter value. * Specify the ApplicationCertificatePath parameter value. * Set the $ApplicationCertificatePassword variable as the ApplicationCertificatePassword parameter value. * Provide the GrantRolesAndPermissions parameter. |

Related Commands

* [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)
* [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5)
* [Add-VBOOrganization](add-vboorganization.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
