---
title: "Remove-VBOProxy"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vboproxy.html"
last_updated: "12/5/2025"
product_version: "8.3.0.2201"
---

# Remove-VBOProxy


Short Description

Removes backup proxy servers.

Syntax

|  |
| --- |
| Remove-VBOProxy -Proxy <VBOProxy> [-Force] [-Credential <PSCredential>] [-WindowsCredential <PSCredential>] [-LinuxCredential <VBOLinuxCredential>] [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet allows you to remove backup proxy servers from the Veeam Backup for Microsoft 365 infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Proxy | Specifies a backup proxy server. The cmdlet will remove this backup proxy server from the Veeam Backup for Microsoft 365 infrastructure. | Accepts the [VBOProxy](vboproxy.md) object.  To get this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | True | Named | True (ByValue) |
| Force | Defines that the cmdlet will remove a backup proxy server without showing warnings in the PowerShell console.  If you do not provide the parameter, the cmdlet will prompt you to confirm the operation.  Default: False | SwitchParameter | False | Named | False |
| Credential | Specifies Windows credentials. The cmdlet will use these credentials to connect to the Windows-based backup proxy server.  If you omit this parameter, the cmdlet will use the Windows credentials under which you are currently logged in.  Note: This parameter will be deprecated in future versions of Veeam Backup for Microsoft 365. Use the WindowsCredential parameter instead. | PSCredential | False | Named | False |
| WindowsCredential | Specifies Windows credentials. The cmdlet will use these credentials to connect to the Windows-based backup proxy server.  If you omit this parameter, the cmdlet will use the Windows credentials under which you are currently logged in. | PSCredential | False | Named | False |
| LinuxCredential | Specifies Linux credentials.  The cmdlet will use these credentials to connect to the Linux-based backup proxy server. | Accepts the [VBOLinuxCredential](vbolinuxcredential.md) object.  To get this object, run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. | False | Named | False |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Removing Windows-Based Backup Proxy Server from Veeam Backup for Microsoft 365 Infrastructure

|  |  |
| --- | --- |
| This example shows how to remove the tech.support.local backup proxy server from the Veeam Backup for Microsoft 365 infrastructure.  |  | | --- | | $proxy = Get-VBOProxy -Hostname tech.support.local  Remove-VBOProxy -Proxy $proxy -Force |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 2. Run the Remove-VBOProxy cmdlet. Set the $proxy variable as the Proxy parameter value. Provide the Force parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Removing Linux-Based Backup Proxy Server from Veeam Backup for Microsoft 365 Infrastructure

|  |  |
| --- | --- |
| This example shows how to remove the linux01 backup proxy server from the Veeam Backup for Microsoft 365 infrastructure.  |  | | --- | | $linuxpwd = ConvertTo-SecureString -String "Pa$$word123" -AsPlainText -Force  $linuxcredentials = New-VBOLinuxCredential -Account "Administrator" -ElevateAccountToRoot:$true -Password $linuxpwd  $proxy = Get-VBOProxy -Hostname linux01  Remove-VBOProxy -Proxy $proxy -LinuxCredential $linuxcredentials |  Perform the following steps:   1. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet. Specify the necessary parameters. Save the result to the $linuxpwd variable. 2. Run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. Specify the necessary parameters. Save the result to the $linuxcredentials variable. 3. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 4. Run the Remove-VBOProxy cmdlet. Set the $proxy variable as the Proxy parameter value. Set the $linuxcredentials variable as the LinuxCredential parameter value. |

Related Commands

* [Get-VBOProxy](get-vboproxy.md)
* [New-VBOLinuxCredential](new-vbolinuxcredential.md)
* [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)


