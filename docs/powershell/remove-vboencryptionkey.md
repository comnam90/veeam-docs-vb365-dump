---
title: "Remove-VBOEncryptionKey"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vboencryptionkey.html"
last_updated: "12/8/2025"
product_version: "8.3.0.2201"
---

# Remove-VBOEncryptionKey


Short Description

Removes encryption keys.

Syntax

|  |
| --- |
| Remove-VBOEncryptionKey -EncryptionKey <VBOEncryptionKey> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes an encryption key for object storage repositories.

|  |
| --- |
| ![Remove-VBOEncryptionKey](images/icon_note.webp) Note |
| You cannot remove an encryption key if it is in use by any of object storage repositories. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| EncryptionKey | Specifies an encryption key. The cmdlet will remove this key from Veeam Backup for Microsoft 365. | Accepts the [VBOEncryptionKey](vboencryptionkey.md) object.  To get this object, run the [Get-VBOEncryptionKey](get-vboencryptionkey.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing Encryption Key

This example shows how to remove an encryption key.

|  |
| --- |
| $key = Get-VBOEncryptionKey -Description "Veeam Admin Key"  Remove-VBOEncryptionKey -EncryptionKey $key |

Perform the following steps:

1. Run the [Get-VBOEncryptionKey](get-vboencryptionkey.md) cmdlet. Specify the Description parameter value. Save the result to the $key variable.
2. Run the Remove-VBOEncryptionKey cmdlet. Set the $key variable as the EncryptionKey parameter value.

Related Commands

[Get-VBOEncryptionKey](get-vboencryptionkey.md)


