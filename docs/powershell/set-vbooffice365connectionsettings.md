---
title: "set-vbooffice365connectionsettings"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbooffice365connectionsettings.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies connection settings to access Microsoft 365 organizations.

Syntax

This cmdlet provides parameter sets that allow you to:

* Modify connection settings to access Microsoft 365 organizations using modern authentication with legacy protocols allowed by specifying an application secret.

|  |
| --- |
| Set-VBOOffice365ConnectionSettings -Settings <VBOOffice365LegacyConnectionSettings> [-AppCredential <PSCredential>] [-GrantRolesAndPermissions] [-ApplicationId <Guid>] [-ApplicationSecret <SecureString>] [<CommonParameters>] |

* Modify connection settings to access Microsoft 365 organizations using basic authentication.

|  |
| --- |
| Set-VBOOffice365ConnectionSettings -Settings <VBOOffice365LegacyConnectionSettings> [-Credential <PSCredential>] [-GrantRolesAndPermissions] [-VeeamAADApplicationUsed] [<CommonParameters>] |

* Modify connection settings to access Microsoft 365 organizations using modern authentication with legacy protocols allowed by specifying an application certificate.

|  |
| --- |
| Set-VBOOffice365ConnectionSettings -Settings <VBOOffice365LegacyConnectionSettings> [-AppCredential <PSCredential>] [-GrantRolesAndPermissions] [-ApplicationId <Guid>] [-ApplicationCertificatePath <String>] [-ApplicationCertificatePassword <SecureString>] [<CommonParameters>] |

Deprecated Cmdlet Set

The following cmdlet set is deprecated. It still works in Veeam Backup for Microsoft 365 8 but may not be supported in the next versions of Veeam Backup for Microsoft 365.

|  |
| --- |
| Set-VBOOffice365ConnectionSettings -Settings <VBOOffice365LegacyConnectionSettings> [-Credential <PSCredential>] [-GrantRolesAndPermissions] [-VeeamAADApplicationUsed] [<CommonParameters>] |

Detailed Description

This cmdlet modifies authentication settings to access Microsoft 365 organizations. You can apply these settings to add Microsoft 365 organizations to the Veeam Backup for Microsoft 365 infrastructure. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Settings | Specifies the authentication settings that you want to modify. | Accepts the VBOOffice365LegacyConnectionSettings object.  To create this object, run the [New-VBOOffice365ConnectionSettings](new-vbooffice365connectionsettings.md) cmdlet. | True | Named | True (ByValue) |
| AppCredential | For the modern authentication type.  Specifies credentials. The cmdlet will use these credentials to connect to a Microsoft 365 organization. | PSCredential | False | Named | False |
| GrantRolesAndPermissions | Defines that the cmdlet will grant required permissions and assign appropriate roles to the account.  Default: False | SwitchParameter | False | Named | False |
| ApplicationId | For the modern authentication type.  Specifies an application ID. The cmdlet will use an application ID to connect to a Microsoft 365 organization. | Guid | False | Named | False |
| ApplicationSecret | For the modern authentication type.  Specifies an application secret. The cmdlet will use an application secret to connect to a Microsoft 365 organization. | SecureString | False | Named | False |
| Credential | Note: This parameter is deprecated.  Specifies credentials. The cmdlet will use these credentials to connect to a Microsoft 365 organization. | PSCredential | False | Named | False |
| VeeamAADApplicationUsed | Defines that the cmdlet will use the Veeam application to connect to Microsoft Graph.  Note: You must set this parameter to true for the following Microsoft Entra regions:   * China * Germany   Default: False | SwitchParameter | False | Named | False |
| ApplicationCertificatePath | For the modern authentication type.  Specifies a path to the application certificate. The cmdlet will use this path to get the application certificate and to connect to a Microsoft 365 organization. | String | False | Named | False |
| ApplicationCertificatePassword | For the modern authentication type.  Specifies the certificate password. The cmdlet will use these credentials to connect to a Microsoft 365 organization. | SecureString | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Connection Settings with Basic Authentication

|  |  |
| --- | --- |
| This example shows how to modify connection settings with the basic authentication of a Microsoft 365 organization with the name ABC.  |  | | --- | | $Credentials = Get-Credential  $Organization = Get-VBOOrganization -Name "ABC"  Set-VBOOffice365ConnectionSettings -Settings $Organization.Office365LegacyConnectionSettings -Credential $Credentials |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet to create a credential object. Enter credentials you want to use for authenticating to a Microsoft 365 organization. Save the result to the $Credentials variable. 2. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet to get an organization with the name ABC. Save the result to the $Organization variable. 3. Run the Set-VBOOffice365ConnectionSettings cmdlet with the $Organization.Office365LegacyConnectionSettings and $Credentials variables to modify the ABC organization connection settings. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Modifying Connection Settings with Modern Authentication Using Application Secret

|  |  |
| --- | --- |
| This example shows how to modify connection settings for a Microsoft 365 organization added using modern authentication with legacy protocols allowed by specifying an application secret.  |  | | --- | | $Credentials = Get-Credential  $Organization = Get-VBOOrganization -Name "ABC"  $ApplicationSecret = ConvertTo-SecureString -String "fCblKbIf+kY10+uB+rROD+wZPT/WxcDNX+EU2O33Q1s=" -AsPlainText -Force  Set-VBOOffice365ConnectionSettings -Settings $Organization.Office365LegacyConnectionSettings -AppCredential $Credentials -ApplicationId d052f06e-1cfa-42ff-9636-9da5e7aa1fd1 -ApplicationSecret $ApplicationSecret -GrantRolesAndPermissions |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet to create a credential object. Enter credentials you want to use for authenticating to a Microsoft 365 organization. Save the result to the $Credentials variable. 2. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet to get an organization with the name ABC. Save the result to the $Organization variable. 3. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet with the AsPlainText parameter to turn the ApplicationSecret into the SecureString type. Save the result to the $ApplicationSecret variable. 4. Run the Set-VBOOffice365ConnectionSettings cmdlet with the $Credentials and $ApplicationSecret variables and the GrantRolesAndPermissions parameter to modify the ABC organization connection settings. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Modifying Connection Settings with Modern Authentication Using Application Certificate

|  |  |
| --- | --- |
| This example shows how to modify connection settings for a Microsoft 365 organization added using modern authentication with legacy protocols allowed by specifying an application certificate.  |  | | --- | | $Credentials = Get-Credential  $Organization = Get-VBOOrganization -Name "ABC"  $ApplicationCertificatePassword = ConvertTo-SecureString -String "fCblKbIf+kY10+uB+rROD+wZPT/WxcDNX+EU2O33Q1s=" -AsPlainText -Force  Set-VBOOffice365ConnectionSettings -Settings $Organization.Office365LegacyConnectionSettings -AppCredential $Credentials -ApplicationId d052f06e-1cfa-42ff-9636-9da5e7aa1fd1 -ApplicationCertificatePath "C:\ApplicationCertificate.pfx" -ApplicationCertificatePassword $ApplicationCertificatePassword |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet to create a credential object. Enter credentials you want to use for authenticating to a Microsoft 365 organization. Save the result to the $Credentials variable. 2. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet to get an organization with the name ABC. Save the result to the $Organization variable. 3. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet with the AsPlainText parameter to turn the ApplicationCertificatePassword into the SecureString type. Save the result to the $ApplicationCertificatePassword variable. 4. Run the Set-VBOOffice365ConnectionSettings cmdlet with the $Credentials and $ApplicationCertificatePassword variables to modify the ABC organization connection settings. |

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5)
* [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
