---
title: "new-vbolinuxcredential"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vbolinuxcredential.html"
last_updated: "2/25/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Creates the Linux credentials record to connect to a Linux-based backup proxy server.

Syntax

|  |
| --- |
| New-VBOLinuxCredential [-SshPort <Int32>] [-ConnectionTimeout <Int32>] -Account <String> [-Password <SecureString>] [-PrivateKeyFilePath <String>] [-Passphrase <SecureString>] [-ElevateAccountToRoot] [-AddToSudoers] [-UseSuIfSudoUnavailable] [-RootPassword <SecureString>] [-Fingerprint <String>] [-PublicKeyBase64 <String>] [-IgnoreFingerprintCheck] [<CommonParameters>] |

Detailed Description

This cmdlet creates the VBOLinuxCredential object. This object contains Linux credentials to connect to a Linux-based backup proxy server.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| SshPort | Specifies a port number. The cmdlet will use this port to connect to a Linux-based backup proxy server through SSH.  Permitted values: 1–65535.  Default: 22 | Int32 | False | Named | False |
| ConnectionTimeout | Specifies the SSH connection timeout in milliseconds. Veeam Backup for Microsoft 365 uses this timeout to wait for connection to a Linux-based backup proxy server through SSH.  Default: 30000 | Int32 | False | Named | False |
| Account | Specifies a user name. The cmdlet will use this account for authentication to a Linux-based backup proxy server. | String | True | Named | False |
| Password | Specifies a password. The cmdlet will use this password for authentication to a Linux-based backup proxy server. | SecureString | False | Named | False |
| PrivateKeyFilePath | For the Identity/Pubkey authentication method.  Specifies the private key file path. | String | False | Named | False |
| Passphrase | For the Identity/Pubkey authentication method.  Specifies a passphrase for a Linux private key. | SecureString | False | Named | False |
| ElevateAccountToRoot | Defines that the cmdlet will provide non-root users with root account privileges.  Default: False | SwitchParameter | False | Named | False |
| AddToSudoers | Defines that the cmdlet will add a user account to sudoers file.  Default: False | SwitchParameter | False | Named | False |
| UseSuIfSudoUnavailable | Defines that Veeam Backup for Microsoft 365 will use the su command if the sudo command is not available.  Default: False | SwitchParameter | False | Named | False |
| RootPassword | Specifies a root password for authentication. | SecureString | False | Named | False |
| Fingerprint | Specifies the SSH host fingerprint. | String | False | Named | False |
| PublicKeyBase64 | Specifies the content of the public key file provided as a Base64 string. | String | False | Named | False |
| IgnoreFingerprintCheck | Defines that Veeam Backup for Microsoft 365 will skip verification of the SSH fingerprint on a target Linux machine.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOLinuxCredential object that contains Linux credentials.

Example

Creating Linux Credentials Record

This example shows how to create a new record with Linux credentials for a Linux-based backup proxy server.

|  |
| --- |
| $linuxpwd = ConvertTo-SecureString -String "Pa$$word123" -AsPlainText -Force  New-VBOLinuxCredential -Account "Administrator" -ElevateAccountToRoot:$true -Password $linuxpwd |

Perform the following steps:

1. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet. Specify the necessary parameters. Save the result to the $linuxpwd variable.
2. Run the New-VBOLinuxCredential cmdlet. Specify the following settings:

* Specify the Account parameter value.
* Set the true value for the ElevateAccountToRoot parameter.
* Set the $linuxpwd variable as the Password parameter value.

Related Commands

[ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)

Page updated 2/25/2025

Page content applies to build 8.3.0.2201
