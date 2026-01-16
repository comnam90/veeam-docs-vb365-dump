---
title: "add-vboproxy"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboproxy.html"
last_updated: "10/14/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Adds a backup proxy server to the Veeam Backup for Microsoft 365 infrastructure.

Syntax

This cmdlet provides parameter sets that allow you to:

* Add Windows-based backup proxy server.

|  |
| --- |
| Add-VBOProxy -Hostname <String> [-Credential <PSCredential>] [-WindowsCredential <PSCredential>] [-Port <Int32>] [-Description <String>] [-Force] [-ThreadsNumber <Int32>] [-EnableNetworkThrottling] [-ThrottlingValue <UInt32>] [-ThrottlingUnit <VBOThrottlingUnit>] [-InternetProxyMode <VBOInternetProxyMode>] [-CustomInternetProxyHostName <String>] [-CustomInternetProxyPort <UInt16>] [-UseCustomInternetProxyAuthentication] [-CustomInternetProxyCredential <PSCredential>] [-UseDomainNetwork] [-ServiceCredential <PSCredential>] [-CreateServiceAccount] [<CommonParameters>] |

* Add Linux-based backup proxy server.

|  |
| --- |
| Add-VBOProxy -Hostname <String> [-Port <Int32>] [-Description <String>] [-Force] [-ThreadsNumber <Int32>] [-EnableNetworkThrottling] [-ThrottlingValue <UInt32>] [-ThrottlingUnit <VBOThrottlingUnit>] [-InternetProxyMode <VBOInternetProxyMode>] [-CustomInternetProxyHostName <String>] [-CustomInternetProxyPort <UInt16>] [-UseCustomInternetProxyAuthentication] [-CustomInternetProxyCredential <PSCredential>] [-LinuxCredential <VBOLinuxCredential>] [-ServiceCredential <PSCredential>] [-CreateServiceAccount] [<CommonParameters>] |

Detailed Description

This cmdlet adds a backup proxy server to the Veeam Backup for Microsoft 365 backup infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Hostname | Specifies a DNS name or an IP address of a backup proxy server that you want to add. | String | True | Named | False |
| Credential | Specifies Windows credentials. The cmdlet will use these credentials to connect to the Windows-based backup proxy server.  If you omit this parameter, the cmdlet will use the Windows credentials under which you are currently logged in.  Note: This parameter will be deprecated in future versions of Veeam Backup for Microsoft 365. Use the WindowsCredential parameter instead. | PSCredential | False | Named | False |
| WindowsCredential | Specifies Windows credentials. The cmdlet will use these credentials to connect to the Windows-based backup proxy server.  If you omit this parameter, the cmdlet will use the Windows credentials under which you are currently logged in. | PSCredential | False | Named | False |
| Port | Specifies a port number. The cmdlet will use this port number to connect to the backup proxy server.  Default: 9193 | Int32 | False | Named | False |
| Description | Specifies a description of the backup proxy server.  The default description contains information on the user who added the backup proxy server, date and time when the backup proxy server was added. | String | False | Named | False |
| Force | Defines that the cmdlet will add a backup proxy server without showing warnings in the PowerShell console.  If you do not provide the parameter, the cmdlet will prompt you to confirm the operation.  Default: False | SwitchParameter | False | Named | False |
| ThreadsNumber | Note: This parameter will be deprecated in future versions of Veeam Backup for Microsoft 365.  Specifies a number of threads that the backup proxy server will simultaneously run to process backup data.  Default: 64 | Int32 | False | Named | False |
| EnableNetworkThrottling | Defines that Veeam Backup for Microsoft 365 will limit the inbound traffic to the backup proxy server for performance optimization.  Default: False | SwitchParameter | False | Named | False |
| ThrottlingValue | For the EnableNetworkThrottling parameter.  Specifies a threshold for the inbound traffic to the backup proxy server.  Default: 0 | UInt32 | False | Named | False |
| ThrottlingUnit | For the EnableNetworkThrottling parameter.  Specifies a measuring unit for the inbound traffic threshold: Mbps, MBs or KBs.  Default: Mbps | VBOThrottlingUnit | False | Named | False |
| InternetProxyMode | Specifies settings of an internet proxy server. Veeam Backup for Microsoft 365 will assign this internet proxy server to a backup proxy that does not have direct access to the internet.   * Custom: Use this option to specify connection settings for an internet proxy server explicitly.  * CustomInternetProxyHostName * CustomInternetProxyPort * UseCustomInternetProxyAuthentication * CustomInternetProxyCredential  * ManagementServerProxy: Use this option if you want an internet proxy server to use the connection settings that are specified in the global internet proxy server settings. * None: Use this option if you do not want to assign an internet proxy server to a backup proxy server. | VBOInternetProxyMode | False | Named | False |
| CustomInternetProxyHostName | For the InternetProxyMode parameter with the Custom option.  Specifies a DNS name or an IP address of the internet proxy server that you want to add. | String | False | Named | False |
| CustomInternetProxyPort | For the InternetProxyMode parameter with the Custom option.  Specifies a port number. A backup proxy will use this port to connect to the internet proxy server.  Default: 3128 | UInt16 | False | Named | False |
| UseCustomInternetProxyAuthentication | For the InternetProxyMode parameter with the Custom option.  Defines that a backup proxy will use authentication for connecting to the internet proxy server.  Default: False | SwitchParameter | False | Named | False |
| CustomInternetProxyCredential | For the InternetProxyMode parameter with the Custom option.  Specifies credentials that you want to use for authentication to the internet proxy server. | PSCredential | False | Named | False |
| UseDomainNetwork | Defines that the cmdlet will add a domain backup proxy, that is, a backup proxy server that resides in the same domain as the Veeam Backup for Microsoft 365 server or in a trusted domain.  If you omit this parameter, the cmdlet will add a workgroup backup proxy, that is, a backup proxy server that resides in a workgroup.  Default: False  For more information about backup proxy server types, see the [Backup Proxy Servers](https://helpcenter.veeam.com/docs/vbo365/guide/vbo_backup_proxy_servers.html?ver=80) section of the Veeam Backup for Microsoft 365 User Guide. | SwitchParameter | False | Named | False |
| ServiceCredential | Specifies credentials of a service account. The cmdlet will use these credentials to run Veeam Backup for Microsoft 365 Proxy Service. | PSCredential | False | Named | False |
| CreateServiceAccount | Defines that the cmdlet will create a service account and automatically grant the required permissions to this account.  Default: False | SwitchParameter | False | Named | False |
| LinuxCredential | Specifies Linux credentials.  The cmdlet will use these credentials to connect to the Linux-based backup proxy server. | Accepts the VBOLinuxCredential object.  To get this object, run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOProxy object that contains settings of a backup proxy server added to the Veeam Backup for Microsoft 365 backup infrastructure.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Adding Backup Proxy Server Using Current Windows Account Credentials

|  |  |
| --- | --- |
| This command adds a Windows-based backup proxy server with 172.70.53.53 IP address to the Veeam Backup for Microsoft 365 server. Veeam Backup for Microsoft 365 will use the account under which you are currently logged in to Windows server to connect to the backup proxy server. The backup proxy server and Veeam Backup for Microsoft 365 server reside in the same domain or in trusted domains.  |  | | --- | | Add-VBOProxy -Hostname 172.70.53.53 -Port 9193 -UseDomainNetwork | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Adding Backup Proxy Server Using Specific Credentials

|  |  |
| --- | --- |
| This example shows how to add a Windows-based backup proxy server with 172.70.53.53 IP address to the Veeam Backup for Microsoft 365 server with the following settings:   * Veeam Backup for Microsoft 365 will use the credentials that you provide to connect to the backup proxy server.  * Veeam Backup for Microsoft 365 will use the 9193 port number to connect to the backup proxy server. * The backup proxy server will reside in a workgroup.   |  | | --- | | $serverCredentials = Get-Credential  Add-VBOProxy -Hostname 172.70.53.53 -WindowsCredential $serverCredentials -Port 9193 |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet. Enter the credentials you want to use to connect to the backup proxy server. Save the result to the $serverCredentials variable. 2. Run the Add-VBOProxy cmdlet. Set the $serverCredentials variable as the WindowsCredential parameter value. Specify the Port parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Adding Backup Proxy Server with Internet Proxy Server Settings

|  |  |
| --- | --- |
| This command adds a Windows-based backup proxy server with the 172.70.53.53 IP address to the Veeam Backup for Microsoft 365 server with the following settings:   * Veeam Backup for Microsoft 365 will use the account under which you are currently logged in to Windows server to connect to the backup proxy server. * The backup proxy will use the internetProxy.local internet proxy server to access the internet. * The backup proxy will use the 3128 port to connect to the CustomInternetProxyPort internet proxy server.   |  | | --- | | Add-VBOProxy -Hostname 172.70.53.53 -InternetProxyMode Custom -CustomInternetProxyHostName internetProxy.local -CustomInternetProxyPort 3128 | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Adding Backup Proxy Server with Inbound Traffic Limitations

|  |  |
| --- | --- |
| This command adds a Windows-based backup proxy server with the 172.70.53.53 IP address to the Veeam Backup for Microsoft 365 server. To connect to the backup proxy server, the cmdlet will use the account under which you are currently logged in.  The threshold for the inbound traffic to the backup proxy will be set to 10 Mbps.  |  | | --- | | Add-VBOProxy -Hostname 172.70.53.53 -EnableNetworkThrottling -ThrottlingValue 10 -ThrottlingUnit Mbps | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 5: Adding Linux-Based Backup Proxy Server

|  |  |
| --- | --- |
| This example shows how to add a Linux-based backup proxy server to the Veeam Backup for Microsoft 365 server with the following settings:   * Veeam Backup for Microsoft 365 will use Linux credentials that you provide to connect to the backup proxy server.  * Veeam Backup for Microsoft 365 will use the 9193 port number to connect to the backup proxy server.   |  | | --- | | $linuxpwd = ConvertTo-SecureString -String "Pa$$word123" -AsPlainText -Force  $linuxcredentials = New-VBOLinuxCredential -Account "Administrator" -ElevateAccountToRoot:$true -Password $linuxpwd  Add-VBOProxy -Hostname linux01 -Port 9193 -LinuxCredential $linuxcredentials |  Perform the following steps:   1. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet. Specify the necessary parameters. Save the result to the $linuxpwd variable. 2. Run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. Specify the necessary parameters. Save the result to the $linuxcredentials variable. 3. Run the Add-VBOProxy cmdlet. Specify the Hostname parameter value. Specify the Port parameter value. Set the $linuxcredentials variable as the LinuxCredential parameter value. |

Related Commands

* [New-VBOLinuxCredential](new-vbolinuxcredential.md)
* [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5)
* [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)

Page updated 10/14/2025

Page content applies to build 8.3.0.2201
