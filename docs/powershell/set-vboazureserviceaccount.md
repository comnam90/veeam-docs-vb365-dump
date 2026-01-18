---
title: "Set-VBOAzureServiceAccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboazureserviceaccount.html"
last_updated: "12/18/2025"
product_version: "8.3.0.2201"
---

# Set-VBOAzureServiceAccount


Short Description

Modifies Microsoft Azure service account settings.

Syntax

This cmdlet provides parameter sets that allow you to:

* Change the Microsoft Azure service account description.

|  |
| --- |
| Set-VBOAzureServiceAccount -Account <VBOAzureServiceAccount> [-Description <String>] [<CommonParameters>] |

* Change the Microsoft Azure service account settings when using the application certificate.

|  |
| --- |
| Set-VBOAzureServiceAccount -Account <VBOAzureServiceAccount> -ApplicationCertificatePath <String> [-ApplicationCertificatePassword <SecureString>] [-Description <String>] [<CommonParameters>] |

* Change the Microsoft Entra application settings.

|  |
| --- |
| Set-VBOAzureServiceAccount -Account <VBOAzureServiceAccount> -ApplicationCertificatePath <String> [-ApplicationCertificatePassword <SecureString>] [-ConfigureApplication] [-Description <String>] [-SubscriptionIds <String[]>] [<CommonParameters>] |

* Change the Microsoft Azure service account settings when using the application secret.

|  |
| --- |
| Set-VBOAzureServiceAccount -Account <VBOAzureServiceAccount> -ApplicationSecret <SecureString> [-Description <String>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies settings for the specified Microsoft Azure service account. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Account | Specifies a Microsoft Azure service account whose settings you want to modify. | Accepts the [VBOAzureServiceAccount](vboazureserviceaccount.md) object.  To get this object, run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. | True | Named | True (ByValue) |
| Description | Specifies a description of Microsoft Azure service account. The cmdlet will replace the current description with the specified description. | String | False | Named | False |
| ApplicationCertificatePath | Specifies a path to the folder where the certificate is located. The cmdlet will import the certificate that is located in this path to set up a secure connection to Microsoft 365 organization. | String | True | Named | False |
| ApplicationCertificatePassword | Specifies the certificate password. The cmdlet will use this password to confirm the certificate that you want to import to a Microsoft Entra application. | SecureString | False | Named | False |
| ConfigureApplication | Defines that the cmdlet will configure settings of an existing Microsoft Entra application: grant the required permissions and register the specified certificate in Microsoft Entra ID.  Default: False | SwitchParameter | True | Named | False |
| SubscriptionIds | Specifies an array of subscriptions associated with a user account that was used to sign in to Microsoft Entra. | String[] | False | Named | False |
| ApplicationSecret | Specifies an application secret. The cmdlet will use an application secret to set up a secure connection to Microsoft 365 organization. | SecureString | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAzureServiceAccount](vboazureserviceaccount.md) object that contains Microsoft Azure service account details.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Microsoft Entra Application Certificate Path and Password

|  |  |
| --- | --- |
| This example shows how to modify a certificate path and password of a Microsoft Entra application associated with the Microsoft Azure service account.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  $account = Get-VBOAzureServiceAccount -Name "Archiver Appliance App"  Set-VBOAzureServiceAccount -Account $account -ApplicationCertificatePath "C:\certificate\newcert.pfx" -ApplicationCertificatePassword $securepassword |  Perform the following steps:   1. Create a new secure password:  1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password.  1. Run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. Specify the Name parameter value. Save the result to the $account variable. 2. Run the Set-VBOAzureServiceAccount cmdlet. Set the $account variable as the Account parameter value. Specify a new value for the ApplicationCertificatePath parameter. Set the $securepassword variable as the ApplicationCertificatePassword parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Modifying Microsoft Entra Application Settings

|  |  |
| --- | --- |
| This example shows how to modify settings of the Microsoft Entra application associated with the Microsoft Azure service account.  |  | | --- | | $account = Get-VBOAzureServiceAccount -Name "Archiver Appliance App"  Set-VBOAzureServiceAccount -Account $account -ApplicationCertificatePath "C:\certificate\cert.pfx" -ConfigureApplication -SubscriptionIds "06b735ac3d-d883-4dd8-8de3-98f49d743012" |  Perform the following steps:   1. Run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. Specify the Name parameter value. Save the result to the $account variable. 2. Run the Set-VBOAzureServiceAccount cmdlet. Set the $account variable as the Account parameter value. Specify the ApplicationCertificatePath parameter value. Specify a new value for the SubscriptionIds parameter. |

Related Commands

* [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)
* [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md)


