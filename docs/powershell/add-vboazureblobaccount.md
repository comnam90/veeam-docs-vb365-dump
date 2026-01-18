---
title: "Add-VBOAzureBlobAccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboazureblobaccount.html"
last_updated: "12/22/2025"
product_version: "8.3.0.2201"
---

# Add-VBOAzureBlobAccount


Short Description

Creates Microsoft Azure Blob Storage account credentials.

Syntax

|  |
| --- |
| Add-VBOAzureBlobAccount -Name <String> -SharedKey <SecureString> [-Description <String>] [<CommonParameters>] |

Detailed Description

This cmdlet creates the [VBOAzureBlobAccount](vboazureblobaccount.md) object. This object contains storage account credentials for Microsoft Azure Blob Storage. Veeam Backup for Microsoft 365 will use these storage account credentials to access Microsoft Azure Blob Storage.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Name | Specifies a login name. The cmdlet will use this login name to add the Microsoft Azure Blob Storage account credentials. | String | True | Named | False |
| SharedKey | Specifies a shared key. The cmdlet will use this shared key to add the Microsoft Azure Blob Storage account credentials. | SecureString | True | Named | False |
| Description | Specifies a description for the Microsoft Azure Blob Storage account credentials. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAzureBlobAccount](vboazureblobaccount.md) object that contains storage account credentials for Microsoft Azure Blob Storage.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Adding Microsoft Azure Blob Storage Credentials Record

|  |  |
| --- | --- |
| This example shows how to add the Microsoft Azure Blob Storage account credentials to Veeam Backup for Microsoft 365.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  Add-VBOAzureBlobAccount -Name "Login" -SharedKey $securepassword |  Perform the following steps:   1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password. 3. Run the Add-VBOAzureBlobAccount cmdlet. Specify the Name parameter value. Set $securepassword as the SharedKey parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Adding Microsoft Azure Blob Storage Credentials Record with Description

|  |  |
| --- | --- |
| This example shows how to add the Microsoft Azure Blob Storage account credentials with a description.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  Add-VBOAzureBlobAccount -SharedKey $securepassword -Name "Login" -Description "Azure Credential Records" |  Perform the following steps:   1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password. 3. Run the Add-VBOAzureBlobAccount cmdlet. Specify the following settings:  * Set $securepassword as the SharedKey parameter value. * Specify the Name parameter value. * Specify the Description parameter value. |

Related Commands

[Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)


