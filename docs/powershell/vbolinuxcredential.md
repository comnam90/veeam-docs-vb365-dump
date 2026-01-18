---
title: "VBOLinuxCredential"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbolinuxcredential.html"
last_updated: "12/8/2025"
product_version: "8.3.0.2201"
---

# VBOLinuxCredential


Contains details about Linux credentials.

| Property | Type | Description |
| --- | --- | --- |
| SshPort | Int | Port number to connect to a Linux-based backup proxy server through SSH.  Default: 22 |
| ConnectionTimeout | Int | The SSH connection timeout to wait for connection to a Linux-based backup proxy server through SSH. |
| Account | String | User name. |
| PrivateKeyFilePath | String | The private key file path. |
| ElevateAccountToRoot | Bool | If True, non-root users are provided with root account privileges. |
| AddToSudoers | Bool | If True, the user account is added to sudoers file. |
| UseSuIfSudoUnavailable | Bool | If True, the su command is used if the sudo command is not available. |
| Fingerprint | String | The SSH host fingerprint. |
| IgnoreFingerprintCheck | Bool | If True, verification of the SSH fingerprint is skipped on a target Linux machine. |

Related Commands

* [Set-VBOConfigurationParameter](set-vboconfigurationparameter.md)
* [Add-VBOProxy](add-vboproxy.md)
* [Set-VBOProxy](set-vboproxy.md)
* [Remove-VBOProxy](remove-vboproxy.md)
* [Update-VBOProxy](update-vboproxy.md)
* [New-VBOLinuxCredential](new-vbolinuxcredential.md)
* [Set-VBOProxyMaintenance](set-vboproxymaintenance.md)


