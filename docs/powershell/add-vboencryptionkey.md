---
title: "add-vboencryptionkey"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboencryptionkey.html"
last_updated: "10/2/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Creates encryption keys for object storage repositories.

Syntax

|  |
| --- |
| Add-VBOEncryptionKey -Password <SecureString> [-Description <String>] [<CommonParameters>] |

Detailed Description

This cmdlet creates an encryption key for object storage repositories. You can use this key to encrypt data that is stored in object storage repositories.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Password | Specifies a password that you want to use to encrypt data. | SecureString | True | Named | False |
| Description | Specifies a description of an encryption key. The cmdlet will create an encryption key with this description. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOEncryptionKey object that contains settings of an encryption key.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Creating Encryption Key

|  |  |
| --- | --- |
| This example shows how to create an encryption key.  |  | | --- | | $plainpassword = "VeeamPassword"  $securepassword = $plainpassword | ConvertTo-SecureString -AsPlainText -Force  Add-VBOEncryptionKey -Password $securepassword |  Perform the following steps:   1. Create the $plainpassword variable and assign a value to it. 2. Create the $securepassword variable and assign it to the $plainpassword variable value. 3. Pipe down the $plainpassword object to the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet. Specify the AsPlainText and the Force variables. 4. Run the Add-VBOEncryptionKey cmdlet. Set the $securepassword variable as the Password parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Creating Encryption Key with Description

|  |  |
| --- | --- |
| This example shows how to create an encryption key with a description.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  Add-VBOEncryptionKey -Password $securepassword -Description "Veeam Administrator" |  Perform the following steps:   1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password. 3. Run the Add-VBOEncryptionKey cmdlet. Set the $securepassword variable as the Password parameter value. Specify the Description parameter value. |

Related Commands

* [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)
* [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)

Page updated 10/2/2025

Page content applies to build 8.3.0.2201
