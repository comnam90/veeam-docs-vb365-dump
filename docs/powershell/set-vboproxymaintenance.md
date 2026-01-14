---
title: "set-vboproxymaintenance"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboproxymaintenance.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Enables or disables maintenance mode for backup proxy servers that are already added to a backup proxy pool.

Syntax

|  |
| --- |
| Set-VBOProxyMaintenance [-WindowsCredential <PSCredential>] [-LinuxCredential <VBOLinuxCredential>] -Proxy <VBOProxy[]> [-Enable] [<CommonParameters>] |

Detailed Description

This cmdlet enables or disables maintenance mode for backup proxy servers that are already added to a backup proxy pool.

If the maintenance mode is enabled for a backup proxy server, Veeam Backup for Microsoft 365 re-assigns all roles of this backup proxy server to another backup proxy server within the same backup proxy pool. All tasks of the unavailable backup proxy server will be continued smoothly by another backup proxy server. Veeam Backup for Microsoft 365 cannot assign new objects for processing to a backup proxy server in the maintenance mode.

You may need to enable the maintenance mode for a backup proxy server, for example, if you want to upgrade a machine assigned the backup proxy server role, or perform other service operations.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| WindowsCredential | Specifies Windows credentials. The cmdlet will use these credentials to connect to the Windows-based backup proxy server.  If you omit this parameter, the cmdlet will use the Windows credentials under which you are currently logged in. | PSCredential | False | Named | False |
| LinuxCredential | Specifies Linux credentials.  The cmdlet will use these credentials to connect to the Linux-based backup proxy server. | Accepts the VBOLinuxCredential object.  To get this object, run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. | False | Named | False |
| Proxy | Specifies an array of backup proxy servers for which you want to enable or disable the maintenance mode. | Accepts the VBOProxy[] object.  To get this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | True | Named | False |
| Enable | Defines that the cmdlet will enable the maintenance mode for the specified backup proxy servers.  Default: True | SwitchParameter | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Enabling Maintenance Mode

|  |  |
| --- | --- |
| This example shows how to enable the maintenance mode for the support.east.local backup proxy server.  |  | | --- | | $serverCredentials = Get-Credential  $proxy = Get-VBOProxy -Hostname support.east.local  Set-VBOProxyMaintenance -Proxy $proxy -WindowsCredential $serverCredentials -Enable:$true |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet. Enter the credentials you want to use to connect to the backup proxy server. Save the result to the $serverCredentials variable. 2. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 3. Run the Set-VBOProxyMaintenance cmdlet. Set the $proxy variable as the Proxy parameter value. Set the $serverCredentials variable as the WindowsCredential parameter value. Set the true value for the Enable parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Disabling Maintenance Mode

|  |  |
| --- | --- |
| This example shows how to disable the maintenance mode for the linux01 backup proxy server.  |  | | --- | | $linuxpwd = ConvertTo-SecureString -String "Pa$$word123" -AsPlainText -Force  $linuxcredentials = New-VBOLinuxCredential -Account "Administrator" -ElevateAccountToRoot:$true -Password $linuxpwd  $proxy = Get-VBOProxy -Hostname linux01  Set-VBOProxyMaintenance -Proxy $proxy -LinuxCredential $linuxcredentials -Enable:$false |  Perform the following steps:   1. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet. Specify the necessary parameters. Save the result to the $linuxpwd variable. 2. Run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. Specify the necessary parameters. Save the result to the $linuxcredentials variable. 3. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 4. Run the Set-VBOProxyMaintenance cmdlet. Set the $proxy variable as the Proxy parameter value. Set the $linuxcredentials variable as the LinuxCredential parameter value. Set the false value for the Enable parameter. |

Related Commands

* [Get-VBOProxy](get-vboproxy.md)
* [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5)
* [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)
* [New-VBOLinuxCredential](new-vbolinuxcredential.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
