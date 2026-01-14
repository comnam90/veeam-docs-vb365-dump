---
title: "new-vboonpremconnectionsettings"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vboonpremconnectionsettings.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Defines connection settings to access on-premises Microsoft organizations.

Syntax

This cmdlet provides parameter sets that allow you to:

* Define connection settings to access on-premises Microsoft Exchange organizations.

|  |
| --- |
| New-VBOOnPremConnectionSettings -Credential <PSCredential> -ServerName <String> [-UseSSL] [-SkipCAVerification] [-SkipCommonNameVerification] [-SkipRevocationCheck] [-ConfigureUserAccount] [-ConfigureThrottlingPolicy] [<CommonParameters>] |

* Define connection settings to access on-premises Microsoft SharePoint organizations.

|  |
| --- |
| New-VBOOnPremConnectionSettings -Credential <PSCredential> -ServerName <String> -ServerPort <UInt16> [-UseSSL] [-SkipCAVerification] [-SkipCommonNameVerification] [-SkipRevocationCheck] [-ConfigureUserAccount] [-ConfigureThrottlingPolicy] [<CommonParameters>] |

Detailed Description

This cmdlet defines connection settings to access on-premises Microsoft organizations. You can apply these settings to add on-premises Microsoft organizations to the Veeam Backup for Microsoft 365 infrastructure.

The cmdlet will create the VBOOnPremConnectionSettings object that contains connection settings to access the following types of on-premises Microsoft organizations:

* On-premises Microsoft Exchange organizations
* On-premises Microsoft SharePoint organizations

Run the [Add-VBOOrganization](add-vboorganization.md) cmdlet to add Microsoft organizations to the Veeam Backup for Microsoft 365 infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Credential | Specifies credentials. The cmdlet will use these credentials to connect to an on-premises Microsoft organization.  Note: You must specify credentials in in one of the following formats:   * Account@domain * Domain\account | PSCredential | True | Named | False |
| ServerName | Specifies a name of an on-premises Microsoft server. The cmdlet will connect to this server. | String | True | Named | False |
| UseSSL | Defines that the cmdlet will enable SSL encryption. The cmdlet will establish secure connection to on-premises Microsoft server using SSL.  Default: False | SwitchParameter | False | Named | False |
| SkipCAVerification | For SSL connection.  Defines that the cmdlet will skip the certificate trusted authority verification.  Default: False | SwitchParameter | False | Named | False |
| SkipCommonNameVerification | For SSL connection.  Defines that the cmdlet will skip the certificate common name verification.  Default: False | SwitchParameter | False | Named | False |
| SkipRevocationCheck | For SSL connection.  Defines that the cmdlet will skip the certificate revocation check.  Default: False | SwitchParameter | False | Named | False |
| ConfigureUserAccount | Defines that the cmdlet will assign the user to the ApplicationImpersonation role.  Default: False | SwitchParameter | False | Named | False |
| ConfigureThrottlingPolicy | Defines that the cmdlet will skip the default Exchange throttling policy and will use the VeeamArchiverThrottlingPolicy that provides unlimited network bandwidth.  Default: False | SwitchParameter | False | Named | False |
| ServerPort | Specifies a port number that the cmdlet will use to connect to the on-premises Microsoft SharePoint server.  Note: This parameter is not required if you want to add the on-premises Microsoft Exchange organization. | UInt16 | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Defining Connection Settings to Microsoft Exchange Organization

|  |  |
| --- | --- |
| This example shows how to create Microsoft Exchange on-premises organization connection settings.  |  | | --- | | $Credentials = Get-Credential  New-VBOOnPremConnectionSettings -Credential $Credentials -ServerName Support.North |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet to create a credential object. Enter credentials you want to use for authenticating to a Microsoft Exchange on-premises organization. Save the result to the $Credentials variable. 2. Run the New-VBOOnPremConnectionSettings cmdlet with the $Credentials variable and the ServerName parameter value to create Microsoft Exchange on-premises organization connection settings. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Defining Connection Settings to Microsoft SharePoint Organization

|  |  |
| --- | --- |
| This example shows how to create Microsoft SharePoint on-premises organization connection settings.  |  | | --- | | $Credentials = Get-Credential  New-VBOOnPremConnectionSettings -Credential $Credentials -ServerName Support.North -ServerPort 5986 |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet to create a credential object. Enter credentials you want to use for authenticating to a Microsoft SharePoint on-premises organization. Save the result to the $Credentials variable. 2. Run the New-VBOOnPremConnectionSettings cmdlet with the $Credentials variable and the ServerName and ServerPort parameters values to create Microsoft SharePoint on-premises organization connection settings. |

Related Commands

[Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
