---
title: "Set-VBOOffice365ApplicationOnlyConnectionSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbooffice365applicationonlyconnectionsettings.html"
last_updated: "1/7/2026"
product_version: "8.3.0.2201"
---

# Set-VBOOffice365ApplicationOnlyConnectionSettings


Short Description

Modifies Microsoft Entra application settings.

Syntax

This cmdlet provides parameter sets that allow you to:

* Modify Microsoft Entra application settings that was added with a user name of a Microsoft Exchange user.

|  |
| --- |
| Set-VBOOffice365ApplicationOnlyConnectionSettings -Settings <VBOApplicationOnlyConnectionSettings> [-ApplicationId <Guid>] [-ApplicationCertificatePath <String>] [-ApplicationCertificatePassword <SecureString>] [-ConfigureApplication] [-SharePointSaveAllWebParts] [<CommonParameters>] |

* Modify Microsoft Entra application settings that was added with an application ID and a new application certificate path.

|  |
| --- |
| Set-VBOOffice365ApplicationOnlyConnectionSettings -Settings <VBOApplicationOnlyConnectionSettings> [-ImpersonationAccountName <String>] [-ApplicationId <Guid>] [-ApplicationCertificatePath <String>] [-ApplicationCertificatePassword <SecureString>] [-ConfigureApplication] [-SharePointSaveAllWebParts] [<CommonParameters>] |

* Modify Microsoft Entra application settings that was added using a Microsoft 365 organization name.

|  |
| --- |
| Set-VBOOffice365ApplicationOnlyConnectionSettings -Settings <VBOApplicationOnlyConnectionSettings> [-OfficeOrganizationName <String>] [-ApplicationId <Guid>] [-ApplicationCertificatePath <String>] [-ApplicationCertificatePassword <SecureString>] [-ConfigureApplication] [-SharePointSaveAllWebParts] [<CommonParameters>] |

* Modify Microsoft Entra application settings that was added using a new certificate path.

|  |
| --- |
| Set-VBOOffice365ApplicationOnlyConnectionSettings -Settings <VBOApplicationOnlyConnectionSettings> [-ApplicationCertificatePath <String>] [-ApplicationCertificatePassword <SecureString>] [-NewApplicationName <String>] [-SharePointSaveAllWebParts] [<CommonParameters>] |

Detailed Description

This cmdlet modifies Microsoft Entra application settings. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Settings | Specifies Microsoft Entra application settings. The cmdlet will modify these settings. | Accepts the [VBOApplicationOnlyConnectionSettings](vboapplicationonlyconnectionsettings.md) object.  To create this object, run the [New-VBOOffice365ApplicationOnlyConnectionSettings](new-vbooffice365applicationonlyconnectionsettings.md) cmdlet. | True | Named | True (ByValue) |
| ApplicationId | Specifies a Microsoft Entra application ID. The cmdlet will use this application ID to set up a secure connection to a Microsoft organization. | Guid | False | Named | False |
| ApplicationCertificatePath | Specifies a path to the folder where the certificate is located. The cmdlet will import the certificate that is located in this path to set up an encrypted connection to a Microsoft organization. | String | False | Named | False |
| ApplicationCertificatePassword | Specifies the certificate password. The cmdlet will use this password to confirm the certificate that you want to import to a Microsoft Entra application. | SecureString | False | Named | False |
| ConfigureApplication | Defines that the cmdlet will configure settings of an existing Microsoft Entra application.  Default: False | SwitchParameter | False | Named | False |
| SharePointSaveAllWebParts | Note: This parameter will be deprecated in future versions of Veeam Backup for Microsoft 365.  Defines that the cmdlet will add SharePoint Web Parts to Microsoft Entra application settings.  Default: False | SwitchParameter | False | Named | False |
| ImpersonationAccountName | Specifies a user name of a Microsoft Exchange user. The cmdlet will use this user name to authenticate to the Microsoft Exchange server. | String | False | Named | False |
| OfficeOrganizationName | Specifies a name of Microsoft 365 organization. The cmdlet will use this name to authenticate to the Microsoft 365 server. | String | False | Named | False |
| NewApplicationName | Specifies a name of a new Microsoft Entra application. The cmdlet will define settings of the Microsoft Entra application with this name. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOApplicationOnlyConnectionSettings](vboapplicationonlyconnectionsettings.md) object that defines Microsoft Entra application settings.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Microsoft Exchange User Name of Microsoft Entra Application Settings

|  |  |
| --- | --- |
| This example shows how to modify a user name of a Microsoft Exchange user added to Microsoft Entra application settings. The cmdlet will replace the Office365Admin@tech-365.tech user name with the Administratortech@tech-365.tech user name.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  $newAppSettings = New-VBOOffice365ApplicationOnlyConnectionSettings -ApplicationCertificatePath "C:\certificate\cert.pfx" -ApplicationCertificatePassword $securepassword -ApplicationId 6c957a12-93fd-469a-86f6-1dc3cc81cf07 -ImpersonationAccountName Office365Admin@tech-365.tech  Set-VBOOffice365ApplicationOnlyConnectionSettings -Settings $newAppSettings -ImpersonationAccountName Administratortech@tech-365.tech |  Perform the following steps:   1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password. 3. Run the [New-VBOOffice365ApplicationOnlyConnectionSettings](new-vbooffice365applicationonlyconnectionsettings.md) cmdlet. Specify the ApplicationCertificatePath, ApplicationCertificatePassword, ApplicationId, and ImpersonationAccountName parameters. Save the result to the $newAppSettings variable. 4. Run the Set-VBOOffice365ApplicationOnlyConnectionSettings cmdlet. Set the $newAppSettings variable as the Settings parameter value. Specify the ImpersonationAccountName parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Modifying Microsoft 365 Organization Name of Microsoft Entra Application Settings

|  |  |
| --- | --- |
| This example shows how to define a name of the Microsoft 365 organization added to Microsoft Entra application settings. The cmdlet will replace the @admin-365.tech organization name with the Administrator-365.tech organization name.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  $newAppSettings = New-VBOOffice365ApplicationOnlyConnectionSettings -OfficeOrganizationName @admin-365.tech -ApplicationId 22b5dd21-5ccf-4696-8482-eda0a1c7d32b -ApplicationCertificatePath "C:\certificate\cert.pfx" -ApplicationCertificatePassword $securepassword  Set-VBOOffice365ApplicationOnlyConnectionSettings -Settings $newAppSettings -OfficeOrganizationName @Administrator-365.tech |  Perform the following steps:   1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password. 3. Run the [New-VBOOffice365ApplicationOnlyConnectionSettings](new-vbooffice365applicationonlyconnectionsettings.md) cmdlet. Specify the OfficeOrganizationName, ApplicationId, ApplicationCertificatePath and ApplicationCertificatePassword parameters. Save the result to the $newAppSettings variable.  1. Run the Set-VBOOffice365ApplicationOnlyConnectionSettings cmdlet. Set the $newAppSettings variable as the Settings parameter value. Specify the OfficeOrganizationName parameter value. |

Related Commands

* [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)
* [New-VBOOffice365ApplicationOnlyConnectionSettings](new-vbooffice365applicationonlyconnectionsettings.md)


