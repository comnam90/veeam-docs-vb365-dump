---
title: "set-vboconfigurationparameter"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboconfigurationparameter.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies configuration of the Veeam Backup for Microsoft 365 controller, backup proxy servers and backup proxy pools.

Syntax

|  |
| --- |
| Set-VBOConfigurationParameter [-WindowsCredential <PSCredential>] [-LinuxCredential <VBOLinuxCredential>] [-Proxy <VBOProxy>] [-ProxyPool <VBOProxyPool>] -XPath <String> -Key <String> [-Value <String>] [-RevertToDefault] [-Restart] [-Controller] [<CommonParameters>] |

Detailed Description

This cmdlet allows you to configure parameters of the controller, backup proxy servers and backup proxy pools. Veeam Backup for Microsoft 365 saves configuration parameters of the Veeam Backup for Microsoft 365 controller to the Config.xml file, configuration parameters of backup proxy servers to the Proxy.xml files.

To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| WindowsCredential | Specifies Windows credentials.  The cmdlet will use these credentials to connect to the Windows-based backup proxy server.  Note: If the ProxyPool parameter is used, you must specify Windows credentials to connect to all Windows-based backup proxy servers in the backup proxy pool. | PSCredential | False | Named | False |
| LinuxCredential | Specifies Linux credentials.  The cmdlet will use these credentials to connect to the Linux-based backup proxy server.  Note: If the ProxyPool parameter is used, you must specify Linux credentials to connect to all Linux-based backup proxy servers in the backup proxy pool. | Accepts the VBOLinuxCredential object.  To get this object, run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. | False | Named | False |
| Proxy | Specifies a backup proxy server.  The cmdlet will configure parameters of this backup proxy server. | Accepts the VBOProxy object.  To get this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | False | Named | False |
| ProxyPool | Specifies a backup proxy pool.  The cmdlet will configure parameters of all backup proxy servers added to this backup proxy pool. | Accepts the VBOProxyPool object.  To get this object, run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. | False | Named | False |
| XPath | Specifies the xpath path in the Config.xml file. | String | True | Named | False |
| Key | Specifies a name of the parameter attribute. | String | True | Named | False |
| Value | Specifies the parameter attribute value. | String | False | Named | False |
| RevertToDefault | Defines that the cmdlet will revert the configuration parameters to the default values.  Default: False | SwitchParameter | False | Named | False |
| Restart | Defines that backup proxy servers will be restarted to apply changes in configuration parameters.  Default: False | SwitchParameter | False | Named | False |
| Controller | Defines that the cmdlet will configure parameters of the Veeam Backup for Microsoft 365 controller.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Configuring Controller Parameters

|  |  |
| --- | --- |
| This example shows how to configure parameters of the Veeam Backup for Microsoft 365 controller.  |  | | --- | | $xpath = "/Veeam/Archiver/Server"  $key = "TestKey"  $value = "TestValue"  Set-VBOConfigurationParameter -XPath $xpath -Key $key -Value $value -Controller |  Perform the following steps:   1. Enter values for the XPath, Key and Value parameters. Save them to the $xpath, $key and $value variables. 2. Run the Set-VBOConfigurationParameter cmdlet. Specify the following settings:  * Set the $xpath variable as the XPath papameter value. * Set the $key variable as the Key parameter value. * Set the $value variable as the Value parameter value. * Provide the Controller parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Configuring Linux-Based Backup Proxy Server Parameters

|  |  |
| --- | --- |
| This example shows how to configure parameters of the Linux-based backup proxy server.  |  | | --- | | $xpath = "/Veeam/Archiver/Server"  $key = "TestKey"  $value = "TestValue"  $vboproxy = Get-VBOProxy -Hostname linux02  $pwd = ConvertTo-SecureString -String "Pa$$word123" -AsPlainText -Force  $linuxcredential = New-VBOLinuxCredential -Account "Administrator" -ElevateAccountToRoot -IgnoreFingerprintCheck -Password $pwd  Set-VBOConfigurationParameter -XPath $xpath -Key $key -Value $value -Proxy $vboproxy -LinuxCredential $linuxcredential -Restart |  Perform the following steps:   1. Enter values for the XPath, Key and Value parameters. Save them to the $xpath, $key and $value variables. 2. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $vboproxy variable. 3. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet. Specify the necessary parameters. Save the result to the $pwd variable. 4. Run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. Specify the necessary parameters. Save the result to the $linuxcredential variable. 5. Run the Set-VBOConfigurationParameter cmdlet. Specify the following settings:  * Set the $xpath variable as the XPath papameter value. * Set the $key variable as the Key parameter value. * Set the $value variable as the Value parameter value. * Set the $vboproxy variable as the Proxy parameter value. * Set the $linuxcredential variable as the LinuxCredential parameter value. * Provide the Restart parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Configuring Backup Proxy Pool Parameters

|  |  |
| --- | --- |
| This example shows how to configure parameters of backup proxy servers added to the backup proxy pool.  |  | | --- | | $xpath = "/Veeam/Archiver/Server"  $key = "TestKey"  $value = "TestValue"  $vboproxypool = Get-VBOProxyPool -Name "Pool"  $winserverCredentials = Get-Credential  $pwd = ConvertTo-SecureString -String "Pa$$word123" -AsPlainText -Force  $linuxcredential = New-VBOLinuxCredential -Account "Administrator" -ElevateAccountToRoot -IgnoreFingerprintCheck -Password $pwd  Set-VBOConfigurationParameter -XPath $xpath -Key $key -Value $value -ProxyPool $vboproxypool -WindowsCredential $winserverCredentials -LinuxCredential $linuxcredential -Restart |  Perform the following steps:   1. Enter values for the XPath, Key and Value parameters. Save them to the $xpath, $key and $value variables. 2. Run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. Specify the Name parameter value. Save the result to the $vboproxypool variable. 3. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet. Enter the credentials you want to use to connect to the backup proxy server. Save the result to the $winserverCredentials variable. 4. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet. Specify the necessary parameters. Save the result to the $pwd variable. 5. Run the [New-VBOLinuxCredential](new-vbolinuxcredential.md) cmdlet. Specify the necessary parameters. Save the result to the $linuxcredential variable. 6. Run the Set-VBOConfigurationParameter cmdlet. Specify the following settings:  * Set the $xpath variable as the XPath papameter value. * Set the $key variable as the Key parameter value. * Set the $value variable as the Value parameter value. * Set the $vboproxypool variable as the ProxyPool parameter value. * Set the $winserverCredentials variable as the WindowsCredential parameter value. * Set the $linuxcredential variable as the LinuxCredential parameter value. * Provide the Restart parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Reverting Configuration Parameters to Default Values

|  |  |
| --- | --- |
| This example shows how to revert configuration parameters of the Windows-based backup proxy server to default values.  |  | | --- | | $xpath = "/Veeam/Archiver/Server"  $key = "TestKey"  $vboproxy = Get-VBOProxy -Hostname 172.17.53.53  $winserverCredentials = Get-Credential  Set-VBOConfigurationParameter -XPath $xpath -Key $key -Proxy $vboproxy -WindowsCredential $winserverCredentials -RevertToDefault -Restart |  Perform the following steps:   1. Enter values for the XPath and Key parameters. Save them to the $xpath and $key variables. 2. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $vboproxy variable. 3. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet. Enter the credentials you want to use to connect to the backup proxy server. Save the result to the $winserverCredentials variable. 4. Run the Set-VBOConfigurationParameter cmdlet. Specify the following settings:  * Set the $xpath variable as the XPath papameter value. * Set the $key variable as the Key parameter value. * Set the $vboproxy variable as the Proxy parameter value. * Set the $winserverCredentials variable as the WindowsCredential parameter value. * Provide the RevertToDefault parameter. * Provide the Restart parameter. |

Related Commands

* [Get-VBOProxy](get-vboproxy.md)
* [Get-VBOProxyPool](get-vboproxypool.md)
* [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)
* [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5)
* [New-VBOLinuxCredential](new-vbolinuxcredential.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
