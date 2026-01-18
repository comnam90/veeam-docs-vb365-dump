---
title: "Set-VBOOnPremConnectionSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboonpremconnectionsettings.html"
last_updated: "1/7/2026"
product_version: "8.3.0.2201"
---

# Set-VBOOnPremConnectionSettings


Short Description

Modifies connection settings to access on-premises Microsoft organizations.

Syntax

This cmdlet provides parameter sets that allow you to:

* Modify connection settings to access on-premises Microsoft Exchange organizations.

|  |
| --- |
| Set-VBOOnPremConnectionSettings -Settings <VBOOnPremConnectionSettings> [-Credential <PSCredential>] [-ServerName <String>] [-UseSSL] [-SkipCAVerification] [-SkipCommonNameVerification] [-SkipRevocationCheck] [-ConfigureUserAccount] [-ConfigureThrottlingPolicy] [<CommonParameters>] |

* Modify connection settings to access on-premises Microsoft SharePoint organizations.

|  |
| --- |
| Set-VBOOnPremConnectionSettings -Settings <VBOOnPremConnectionSettings> [-Credential <PSCredential>] [-ServerName <String>] [-ServerPort <UInt16>] [-UseSSL] [-SkipCAVerification] [-SkipCommonNameVerification] [-SkipRevocationCheck] [<CommonParameters>] |

Detailed Description

This cmdlet modifies connection settings to access on-premises Microsoft organizations. You can apply these settings to add on-premises Microsoft organizations to the Veeam Backup for Microsoft 365 infrastructure. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Settings | Specifies the authentication settings that you want to modify. | Accepts the [VBOOnPremConnectionSettings](vboonpremconnectionsettings.md) object.  To create this object, run the [New-VBOOnPremConnectionSettings](new-vboonpremconnectionsettings.md) cmdlet. | True | Named | True (ByValue) |
| Credential | Specifies credentials. The cmdlet will use these credentials to connect to an on-premises Microsoft organization.  Note: You must specify credentials in in one of the following formats:   * Account@domain * Domain\account | PSCredential | False | Named | False |
| ServerName | Specifies a name of an on-premises Microsoft server. The cmdlet will connect to this server. | String | False | Named | False |
| UseSSL | Defines that the cmdlet will enable SSL encryption. The cmdlet will establish secure connection to on-premises Microsoft server using SSL.  Default: False | SwitchParameter | False | Named | False |
| SkipCAVerification | For SSL connection.  Defines that the cmdlet will skip the certificate trusted authority verification.  Default: False | SwitchParameter | False | Named | False |
| SkipCommonNameVerification | For SSL connection.  Defines that the cmdlet will skip the certificate common name verification.  Default: False | SwitchParameter | False | Named | False |
| SkipRevocationCheck | For SSL connection.  Defines that the cmdlet will skip the certificate revocation check.  Default: False | SwitchParameter | False | Named | False |
| ConfigureUserAccount | Defines that the cmdlet will assign the user to the ApplicationImpersonation role.  Default: False | SwitchParameter | False | Named | False |
| ConfigureThrottlingPolicy | Defines that the cmdlet will skip the default Exchange throttling policy and will use the VeeamArchiverThrottlingPolicy that provides unlimited network bandwidth.  Default: False | SwitchParameter | False | Named | False |
| ServerPort | Specifies a port number that the cmdlet will use to connect to the on-premises Microsoft SharePoint server.  Note: This parameter is not required if you want to add the on-premises Microsoft Exchange organization. | UInt16 | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Connection Settings for Microsoft Exchange Organization

|  |  |
| --- | --- |
| This example shows how to modify connection settings for a Microsoft Exchange on-premises organization with the name ABC.  |  | | --- | | $Credentials = Get-Credential  $Organization = Get-VBOOrganization -Name "ABC"  Set-VBOOnPremConnectionSettings -Settings $Organization.OnPremConnectionSettings -Credential $Credentials -ServerName Support.North |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet to create a credential object. Enter credentials you want to use for authenticating to a Microsoft Exchange on-premises organization. Save the result to the $Credentials variable. 2. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet to get an organization with the name ABC. Save the result to the $Organization variable. 3. Run the Set-VBOOnPremConnectionSettings cmdlet with the $Organization.OnPremConnectionSettings and $Credentials variables and the ServerName parameter value to modify the connection settings for a Microsoft Exchange on-premises organization with the name ABC. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Modifying Connection Settings for Microsoft SharePoint Organization

|  |  |
| --- | --- |
| This example shows how to modify connection settings for a Microsoft SharePoint on-premises organization with the name ABC.  |  | | --- | | $Credentials = Get-Credential  $Organization = Get-VBOOrganization -Name "ABC"  Set-VBOOnPremConnectionSettings -Settings $Organization.OnPremConnectionSettings -Credential $Credentials -ServerName Support.North -ServerPort 5986 |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet to create a credential object. Enter credentials you want to use for authenticating to a Microsoft SharePoint organization. Save the result to the $Credentials variable. 2. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet to get an organization with the name ABC. Save the result to the $Organization variable. 3. Run the Set-VBOOnPremConnectionSettings cmdlet with the $Organization.OnPremConnectionSettings and $Credentials variables and the ServerName and ServerPort parameters values to modify the connection settings for a Microsoft SharePoint on-premises organization with the name ABC. |

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5)


