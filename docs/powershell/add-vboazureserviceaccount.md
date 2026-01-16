---
title: "add-vboazureserviceaccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboazureserviceaccount.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Creates Microsoft Azure service accounts that are required to use the Azure archiver appliance when transferring backed-up data between different instances of Azure Blob Storage or to Azure Blob Storage Archive.

Syntax

This cmdlet provides parameter sets that allow you to:

* Use an existing Microsoft Entra application and authenticate to Microsoft 365 with an application certificate.

|  |
| --- |
| Add-VBOAzureServiceAccount -Region <VBOAzureRegionType> -TenantId <String> -ApplicationId <Guid> -ApplicationCertificatePath <String> [-ApplicationCertificatePassword <SecureString>] [-ConfigureApplication] [-Description <String>] [-SubscriptionIds <String[]>] [<CommonParameters>] |

* Register a new Microsoft Entra application in Microsoft Entra ID.

|  |
| --- |
| Add-VBOAzureServiceAccount -Region <VBOAzureRegionType> [-TenantId <String>] -ApplicationName <String> -ApplicationCertificatePath <String> [-ApplicationCertificatePassword <SecureString>] [-Description <String>] -SubscriptionIds <String[]> [<CommonParameters>] |

* Use an existing Microsoft Entra application and authenticate to Microsoft 365 with an application secret.

|  |
| --- |
| Add-VBOAzureServiceAccount -Region <VBOAzureRegionType> -TenantId <String> -ApplicationId <Guid> -ApplicationSecret <SecureString> [-ConfigureApplication] [-Description <String>] [-SubscriptionIds <String[]>] [<CommonParameters>] |

Detailed Description

This cmdlet creates the VBOAzureServiceAccount object. This object contains details of the Microsoft Azure service account that is required to use the Azure archiver appliance when transferring backed-up data between different instances of Azure Blob Storage or to Azure Blob Storage Archive.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Region | Specifies a Microsoft Entra region. You can select the following types of region:   * Global * Germany * China * Government | VBOAzureRegionType | True | Named | False |
| TenantId | Specifies an ID of the Microsoft 365 organization in Microsoft Entra. | String | True | Named | False |
| ApplicationId | Specifies a Microsoft Entra application ID. The cmdlet will use this application ID to set up a secure connection to Microsoft 365 organization. | Guid | True | Named | False |
| ApplicationCertificatePath | Specifies a path to the folder where the certificate is located. The cmdlet will import the certificate that is located in this path to set up a secure connection to Microsoft 365 organization. | String | True | Named | False |
| ApplicationCertificatePassword | Specifies the certificate password. The cmdlet will use this password to confirm the certificate that you want to import to a Microsoft Entra application. | SecureString | False | Named | False |
| ConfigureApplication | Defines that the cmdlet will configure settings of an existing Microsoft Entra application: grant the required permissions and register the specified certificate in Microsoft Entra ID.  Default: False | SwitchParameter | False | Named | False |
| Description | Specifies a description of Microsoft Azure service account.  The default description contains information on the user who created the Microsoft Azure service account, date and time when the Microsoft Azure service account was created. | String | False | Named | False |
| SubscriptionIds | Specifies an array of subscriptions associated with a user account that was used to sign in to Microsoft Entra. | String[] | False | Named | False |
| ApplicationName | Specifies a name of a new Microsoft Entra application. The cmdlet will register a Microsoft Entra application with this name in Microsoft Entra ID. | String | True | Named | False |
| ApplicationSecret | Specifies an application secret. The cmdlet will use an application secret to set up a secure connection to Microsoft 365 organization. | SecureString | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAzureServiceAccount object that contains Microsoft Azure service account details.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Creating Microsoft Azure Service Account Through Registering New Microsoft Entra Application

|  |  |
| --- | --- |
| This example shows how to create a Microsoft Azure service account through registering a new Microsoft Entra application. The cmdlet will add the application to Microsoft Entra ID, grant the required permissions and register the specified certificate.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  Add-VBOAzureServiceAccount -Region Global -ApplicationName "Archiver Appliance App" -ApplicationCertificatePath "C:\certificate\cert.pfx" -ApplicationCertificatePassword $securepassword -SubscriptionIds "l8e5ac3d-d883-4dd8-8de3-a8f315fb6ae2","06b7354e-518f-4a10-b4c1-98f49d743012"  WARNING: To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code DRW34WGBN to authenticate. |  Perform the following steps:   1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password. 3. Run the Add-VBOAzureServiceAccount cmdlet. Specify the following settings:  * Specify the Region parameter value. * Specify the ApplicationName parameter value. * Specify the ApplicationCertificatePath parameter value. * Set the $securepassword variable as the ApplicationCertificatePassword parameter value. * Specify the SubscriptionIds parameter value.  1. To set up a secure connection to a Microsoft organization, open the <https://microsoft.com/devicelogin> link in a browser and enter the code that you get in the PowerShell Console to authenticate to the Microsoft 365 server. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Creating Microsoft Azure Service Account Through Using Existing Microsoft Entra Application with Application Certificate

|  |  |
| --- | --- |
| This example shows how to create a Microsoft Azure service account through using the existing Microsoft Entra application and authenticate to Microsoft 365 with an application certificate, grant the required permissions to Microsoft Entra application and register the specified certificate in Microsoft Entra ID.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  Add-VBOAzureServiceAccount -Region Global -TenantId "721185d3-7da3-41e0-9452-31342a27c9d1" -ApplicationId dde4daf4-44ff-44a4-9559-53ccc65c500a -ApplicationCertificatePath "C:\certificate\cert.pfx" -ApplicationCertificatePassword $securepassword -ConfigureApplication -SubscriptionIds "l8e5ac3d-d883-4dd8-8de3-a8f315fb6ae2","06b7354e-518f-4a10-b4c1-98f49d743012" |  Perform the following steps:   1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password. 3. Run the Add-VBOAzureServiceAccount cmdlet. Specify the following settings:  * Specify the Region parameter value. * Specify the TenantId parameter value. * Specify the ApplicationId parameter value. * Specify the ApplicationCertificatePath parameter value. * Set the $securepassword variable as the ApplicationCertificatePassword parameter value. * Provide the ConfigureApplication parameter. * Specify the SubscriptionIds parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Creating Microsoft Azure Service Account Through Using Existing Microsoft Entra Application with Application Secret

|  |  |
| --- | --- |
| This example shows how to create a Microsoft Azure service account through using the existing Microsoft Entra application and authenticate to Microsoft 365 with an application secret, grant the required permissions to Microsoft Entra application and register the application certificate in Microsoft Entra ID.  |  | | --- | | $applicationSecret = ConvertTo-SecureString -String "fCblKbIf+kY10+uB+rROD+wZPT/WxcDNX+EU2O33Q1s=" -AsPlainText -Force  Add-VBOAzureServiceAccount -Region Global -TenantId "721185d3-7da3-41e0-9452-31342a27c9d1" -ApplicationId dde4daf4-44ff-44a4-9559-53ccc65c500a -ApplicationSecret $applicationSecret -ConfigureApplication -SubscriptionIds "l8e5ac3d-d883-4dd8-8de3-a8f315fb6ae2","06b7354e-518f-4a10-b4c1-98f49d743012" |  Perform the following steps:   1. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet to convert the plain text to the secure string. Specify the String parameter value. Provide the AsPlainText parameter to turn the plain text to the secure string. Provide the Force parameter. Save the result to the $applicationSecret variable. 2. Run the Add-VBOAzureServiceAccount cmdlet. Specify the following settings:  * Specify the Region parameter value. * Specify the TenantId parameter value. * Specify the ApplicationId parameter value.  * Set the $applicationSecret variable as ApplicationSecret parameter value. * Provide the ConfigureApplication parameter. * Specify the SubscriptionIds parameter value. |

Related Commands

* [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)
* [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
