---
title: "update-vboproxy"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/update-vboproxy.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Upgrades backup proxy servers.

Syntax

|  |
| --- |
| Update-VBOProxy [-Credential <PSCredential>] [-WindowsCredential <PSCredential>] [-LinuxCredential <VBOLinuxCredential>] -Proxy <VBOProxy[]> [<CommonParameters>] |

Detailed Description

This cmdlet upgrades an array of backup proxy servers. You may need this if you have upgraded Veeam Backup for Microsoft 365 to a new version and all backup proxy servers configured in your environment are marked as Out of Date.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Credential | Specifies Windows credentials. The cmdlet will use these credentials to connect to the Windows-based backup proxy server.  If you omit this parameter, the cmdlet will use the Windows credentials under which you are currently logged in.  Note: This parameter will be deprecated in future versions of Veeam Backup for Microsoft 365. Use the WindowsCredential parameter instead. | PSCredential | False | Named | False |
| WindowsCredential | Specifies Windows credentials. The cmdlet will use these credentials to connect to the Windows-based backup proxy server.  If you omit this parameter, the cmdlet will use the Windows credentials under which you are currently logged in. | PSCredential | False | Named | False |
| LinuxCredential | Specifies Linux credentials.  The cmdlet will use these credentials to connect to the Linux-based backup proxy server. | Accepts the VBOLinuxCredential object.  To get this object, run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. | False | Named | False |
| Proxy | Specifies an array of backup proxy servers. The cmdlet will upgrade these backup proxy servers. | Accepts the VBOProxy[] object.  To get this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Upgrading All Backup Proxy Servers

|  |  |
| --- | --- |
| This example shows how to upgrade all backup proxy servers that are added to Veeam Backup for Microsoft 365.  |  | | --- | | $proxy = Get-VBOProxy  Update-VBOProxy -Proxy $proxy |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Save the result to the $proxy variable. 2. Run the Update-VBOProxy cmdlet. Set the $proxy variable as the Proxy parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Upgrading Windows-Based Backup Proxy Server

|  |  |
| --- | --- |
| This example shows how to upgrade the proxy03.tech.local backup proxy server that is added to Veeam Backup for Microsoft 365. To connect to the backup proxy server, the cmdlet will use current account credentials.  |  | | --- | | $proxy = Get-VBOProxy -Hostname proxy03.tech.local  Update-VBOProxy -Proxy $proxy |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 2. Run the Update-VBOProxy cmdlet. Set the $proxy variable as the Proxy parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Upgrading Windows-Based Backup Proxy Server with Windows Credentials

|  |  |
| --- | --- |
| This example shows how to upgrade the proxy03.tech.local backup proxy server that is added to Veeam Backup for Microsoft 365. To connect to the backup proxy server, the cmdlet will use the backup proxy server credentials.  |  | | --- | | $proxy = Get-VBOProxy -Hostname proxy03.tech.local  $credentials = Get-Credential  Update-VBOProxy -Proxy $proxy -WindowsCredential $credentials |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 2. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet to create a credential object. Enter credentials that will be used to connect to the proxy server. Save the result to the $credentials variable. 3. Run the Update-VBOProxy cmdlet. Specify the $proxy variable as the Proxy parameter value. Specify $credentials variable as the WindowsCredential parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Upgrading Linux-Based Backup Proxy Server

|  |  |
| --- | --- |
| This example shows how to upgrade the linux01 backup proxy server that is added to Veeam Backup for Microsoft 365.  |  | | --- | | $linuxpwd = ConvertTo-SecureString -String "Pa$$word123" -AsPlainText -Force  $linuxcredentials = New-VBOLinuxCredential -Account "Administrator" -ElevateAccountToRoot:$true -Password $linuxpwd  $proxy = Get-VBOProxy -Hostname linux01  Update-VBOProxy -Proxy $proxy -LinuxCredential $linuxcredentials |  Perform the following steps:   1. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet. Specify the necessary parameters. Save the result to the $linuxpwd variable. 2. Run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. Specify the necessary parameters. Save the result to the $linuxcredentials variable. 3. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 4. Run the Update-VBOProxy cmdlet. Set the $proxy variable as the Proxy parameter value. Set the $linuxcredentials variable as the LinuxCredential parameter value. |

Related Commands

* [Get-VBOProxy](get-vboproxy.md)
* [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5)
* [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)
* [New-VBOLinuxCredential](new-vbolinuxcredential.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
