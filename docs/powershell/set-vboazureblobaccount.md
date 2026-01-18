---
title: "Set-VBOAzureBlobAccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboazureblobaccount.html"
last_updated: "12/22/2025"
product_version: "8.3.0.2201"
---

# Set-VBOAzureBlobAccount


Short Description

Modifies Microsoft Azure Blob Storage account credentials.

Syntax

|  |
| --- |
| Set-VBOAzureBlobAccount -Account <VBOAzureBlobAccount> [-Name <String>] [-SharedKey <SecureString>] [-Description <String>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies storage account credentials for Microsoft Azure Blob Storage. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Account | Specifies Microsoft Azure Blob Storage account credentials that you want to modify. | Accepts the [VBOAzureBlobAccount](vboazureblobaccount.md) object.  To get this object, run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. | True | Named | False |
| Name | Specifies the Microsoft Azure Blob login name. The cmdlet will add this login name to Microsoft Azure Blob Storage account credentials. | String | False | Named | False |
| SharedKey | Specifies a shared key. The cmdlet will use this shared key to add Microsoft Azure Blob Storage account credentials. | SecureString | False | Named | False |
| Description | Specifies a description. The cmdlet will add this description to Microsoft Azure Blob Storage account credentials. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAzureBlobAccount](vboazureblobaccount.md) object that contains storage account credentials for Microsoft Azure Blob Storage.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Shared Key for Microsoft Azure Blob Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to modify a shared key of the storage account credentials for Microsoft Azure Blob Storage.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  $account = Get-VBOAzureBlobAccount -Name "Microsoft Azure Blob"  Set-VBOAzureBlobAccount -Account $account -SharedKey $securepassword |  Perform the following steps:   1. Create a new secure password:  1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password.  1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the Set-VBOAzureBlobAccount cmdlet. Set the $account variable as the Account parameter value. Set the $securepassword as the SharedKey parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Modifying Login Name for Microsoft Azure Blob Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to modify a login name of the storage account credentials for Microsoft Azure Blob Storage.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Name "Microsoft Azure Blob"  $key = Get-VBOEncryptionKey  Set-VBOAzureBlobAccount -Account $account -SharedKey $key -Name "Veeam Azure" |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the [Get-VBOEncryptionKey](get-vboencryptionkey.md) cmdlet. Save the result to the $key variable. 3. Run the Set-VBOAzureBlobAccount cmdlet. Specify the following settings:  * Set the $account variable as the Account parameter value. * Set the $key variable as the SharedKey parameter value. * Specify the Name parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Modifying Description for Microsoft Azure Blob Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to modify a description of the storage account credentials for Microsoft Azure Blob Storage.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Name "Veeam Azure Admin"  $key = Get-VBOEncryptionKey  Set-VBOAzureBlobAccount -Account $account -SharedKey $key -Description "Veeam Azure Administrator" |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the [Get-VBOEncryptionKey](get-vboencryptionkey.md) cmdlet. Save the result to the $key variable.  1. Run the Set-VBOAzureBlobAccount cmdlet. Specify the following settings:  * Set the $account variable as the Account parameter value. * Set the $key variable as the SharedKey parameter value. * Specify the Description parameter value. |

Related Commands

* [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)
* [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md)
* [Get-VBOEncryptionKey](get-vboencryptionkey.md)


