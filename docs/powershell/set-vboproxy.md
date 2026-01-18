---
title: "Set-VBOProxy"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboproxy.html"
last_updated: "12/5/2025"
product_version: "8.3.0.2201"
---

# Set-VBOProxy


Short Description

Modifies settings of a backup proxy server.

Syntax

|  |
| --- |
| Set-VBOProxy -Proxy <VBOProxy> [-Credential <PSCredential>] [-WindowsCredential <PSCredential>] [-Description <String>] [-Port <Int32>] [-ThreadsNumber <Int32>] [-EnableNetworkThrottling] [-ThrottlingValue <UInt32>] [-ThrottlingUnit <VBOThrottlingUnit>] [-InternetProxyMode <VBOInternetProxyMode>] [-CustomInternetProxyHostName <String>] [-CustomInternetProxyPort <UInt16>] [-UseCustomInternetProxyAuthentication] [-CustomInternetProxyCredential <PSCredential>] [-LinuxCredential <VBOLinuxCredential>]  [<CommonParameters>] |

Detailed Description

This cmdlet modifies settings of a backup proxy that is added to the Veeam Backup for Microsoft 365 infrastructure. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Proxy | Specifies a backup proxy server.  The cmdlet will modify settings of this backup proxy server. | Accepts the [VBOProxy](vboproxy.md) object.  To get this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | True | Named | True (ByValue) |
| Credential | Specifies Windows credentials. The cmdlet will use these credentials to connect to the Windows-based backup proxy server.  If you omit this parameter, the cmdlet will use the Windows credentials under which you are currently logged in.  Note: This parameter will be deprecated in future versions of Veeam Backup for Microsoft 365. Use the WindowsCredential parameter instead. | PSCredential | False | Named | False |
| WindowsCredential | Specifies Windows credentials. The cmdlet will use these credentials to connect to the Windows-based backup proxy server.  If you omit this parameter, the cmdlet will use the Windows credentials under which you are currently logged in. | PSCredential | False | Named | False |
| Description | Specifies a description of the backup proxy server.  The cmdlet will replace the current description with the specified description. | String | False | Named | False |
| Port | Specifies a port number. The cmdlet will use this port number to connect to the backup proxy server.  Default: 9193 | Int32 | False | Named | False |
| ThreadsNumber | Note: This parameter will be deprecated in future versions of Veeam Backup for Microsoft 365.  Specifies a number of threads that the backup proxy server will simultaneously run to process backup data.  Default: 64 | Int32 | False | Named | False |
| EnableNetworkThrottling | Defines that Veeam Backup for Microsoft 365 will limit the inbound traffic to the backup proxy server for performance optimization.  Default: False | SwitchParameter | False | Named | False |
| ThrottlingValue | For the EnableNetworkThrottling parameter.  Specifies a threshold for the inbound traffic to the backup proxy server.  Default: 0 | UInt32 | False | Named | False |
| ThrottlingUnit | For the EnableNetworkThrottling parameter.  Specifies a measuring unit for the inbound traffic threshold: Mbps, MBs or KBs.  Default: Mbps | VBOThrottlingUnit | False | Named | False |
| InternetProxyMode | Specifies settings of an internet proxy server. Veeam Backup for Microsoft 365 will assign this internet proxy server to a backup proxy that does not have direct access to the internet.   * Custom: Use this option to specify connection settings for an internet proxy server explicitly.  * CustomInternetProxyHostName * CustomInternetProxyPort * UseCustomInternetProxyAuthentication * CustomInternetProxyCredential  * ManagementServerProxy: Use this option if you want an internet proxy server to use the connection settings that are specified in the global internet proxy server settings. * None: Use this option if you do not want to assign an internet proxy server to a backup proxy server. | VBOInternetProxyMode | False | Named | False |
| CustomInternetProxyHostName | For the InternetProxyMode parameter with the Custom option.  Specifies a DNS name or an IP address of the internet proxy server that you want to add. | String | False | Named | False |
| CustomInternetProxyPort | For the InternetProxyMode parameter with the Custom option.  Specifies a port number. The backup proxy will use this port to connect to the internet proxy server.  Default: 3128 | UInt16 | False | Named | False |
| UseCustomInternetProxyAuthentication | For the InternetProxyMode parameter with the Custom option.  Defines that the backup proxy will use authentication for connecting to the internet proxy server.  Default: False | SwitchParameter | False | Named | False |
| CustomInternetProxyCredential | For the InternetProxyMode parameter with the Custom option.  Specifies credentials that you want to use for authentication to the internet proxy server. | PSCredential | False | Named | False |
| LinuxCredential | Specifies Linux credentials.  The cmdlet will use these credentials to connect to the Linux-based backup proxy server. | Accepts the [VBOLinuxCredential](vbolinuxcredential.md) object.  To get this object, run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOProxy](vboproxy.md) object that contains a list of backup proxy servers added to the Veeam Backup for Microsoft 365 backup infrastructure.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Inbound Traffic Limitations for Backup Proxy Server

|  |  |
| --- | --- |
| This example shows how to modify a backup proxy server with the ID d96f55a4-d15d-410b-b0f0-d51d17ccdab6. Veeam Backup for Microsoft 365 will use the credentials that you provide to connect to the backup proxy server.  The threshold for the inbound traffic to the backup proxy will be set to 10 Mbps.  |  | | --- | | $proxy = Get-VBOProxy -Id d96f55a4-d15d-410b-b0f0-d51d17ccdab6  Set-VBOProxy -Proxy $proxy -EnableNetworkThrottling -ThrottlingValue 10 -ThrottlingUnit Mbps |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Id parameter value. Save the result to the $proxy variable. 2. Run the Set-VBOProxy cmdlet. Specify the following settings:  * Set the $proxy variable as the Proxy parameter value. * Provide the EnableNetworkThrottling parameter. * Specify the ThrottlingValue parameter value. * Specify the ThrottlingUnit parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Modifying Windows Credentials for Backup Proxy Server

|  |  |
| --- | --- |
| This example shows how to change Windows credentials that Veeam Backup for Microsoft 365 uses to connect to the support.east.local backup proxy server.  |  | | --- | | $serverCredentials = Get-Credential  $proxy = Get-VBOProxy -Hostname support.east.local  Set-VBOProxy -Proxy $proxy -WindowsCredential $serverCredentials |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet. Enter the credentials you want to use to connect to the backup proxy server. Save the result to the $serverCredentials variable. 2. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 3. Run the Set-VBOProxy cmdlet. Set the $proxy variable as the Proxy parameter value. Set the $serverCredentials variable as the WindowsCredential parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Modifying Internet Proxy Server Settings for Backup Proxy Server

|  |  |
| --- | --- |
| This example shows how modify settings that the support.east.local proxy server uses to connect to the internetProxy.local internet proxy server. The support.east.local backup proxy server will use the default port to connect to the internet proxy server.  |  | | --- | | $proxy = Get-VBOProxy -Hostname support.east.local  Set-VBOProxy -Proxy $proxy -InternetProxyMode Custom -CustomInternetProxyHostName internetProxy.local -CustomInternetProxyPort 3128 |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 2. Run the Set-VBOProxy cmdlet. Specify the following settings:  * Set the $proxy variable as the Proxy parameter value. * Set Custom as the InternetProxyMode parameter value. * Specify the CustomInternetProxyHostName parameter value. * Specify the CustomInternetProxyPort parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Modifying Linux Credentials for Backup Proxy Server

|  |  |
| --- | --- |
| This example shows how to change Linux credentials that Veeam Backup for Microsoft 365 uses to connect to the linux01 backup proxy server.  |  | | --- | | $linuxpwd = ConvertTo-SecureString -String "Pa$$word123" -AsPlainText -Force  $newlinuxcredentials = New-VBOLinuxCredential -Account "Administrator2" -ElevateAccountToRoot:$true -Password $linuxpwd  $proxy = Get-VBOProxy -Hostname linux01  Set-VBOProxy -Proxy $proxy -LinuxCredential $newlinuxcredentials |  Perform the following steps:   1. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet. Specify the necessary parameters. Save the result to the $linuxpwd variable. 2. Run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. Specify the necessary parameters. Save the result to the $newlinuxcredentials variable. 3. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 4. Run the Set-VBOProxy cmdlet. Set the $proxy variable as the Proxy parameter value. Set the $newlinuxcredentials variable as the LinuxCredential parameter value. |

Related Commands

* [Get-VBOProxy](get-vboproxy.md)
* [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5)
* [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)
* [New-VBOLinuxCredential](new-vbolinuxcredential.md)


