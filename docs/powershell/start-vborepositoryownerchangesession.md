---
title: "Start-VBORepositoryOwnerChangeSession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/start-vborepositoryownerchangesession.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Start-VBORepositoryOwnerChangeSession


Short Description

Creates and starts a change owner session to move a backup repository to another backup proxy server or backup proxy pool.

Syntax

This cmdlet provides parameter sets that allow you to:

* Create and start a change owner session to move a backup repository or an object storage repository to another backup proxy server.

|  |
| --- |
| Start-VBORepositoryOwnerChangeSession -Repository <VBORepository> [-Proxy <VBOProxy>] [-WaitForSessionsTimeoutMinutes <Int32>] [-ForceStopSessions] [-ForceStopSessionsTimeoutMinutes <Int32>] [-IgnoreConnectionTroublesToSourceLocation] [-Force] [<CommonParameters>] |

* Create and start a change owner session to move an object storage repository to another backup proxy pool.

|  |
| --- |
| Start-VBORepositoryOwnerChangeSession -Repository <VBORepository> [-Pool <VBOProxyPool>] [-WaitForSessionsTimeoutMinutes <Int32>] [-ForceStopSessions] [-ForceStopSessionsTimeoutMinutes <Int32>] [-IgnoreConnectionTroublesToSourceLocation] [-Force] [<CommonParameters>] |

Detailed Description

This cmdlet creates and starts a session when Veeam Backup for Microsoft 365 moves a backup repository to another backup proxy server or backup proxy pool.

|  |
| --- |
| ![Start-VBORepositoryOwnerChangeSession](images/icon_note.webp) Note |
| Starting many change owner sessions may overload the NATS server resulting session failures. To prevent this, use the [Get-VBORepositoryOwnerChangeSession](get-vborepositoryownerchangesession.md) cmdlet to check the status of a particular change owner session and wait for each session to complete. Alternatively, you can insert a delay between change owner sessions. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Repository | Specifies a backup repository or an object storage repository. The cmdlet will create and start a change owner session for this backup repository or object storage repository. | Accepts the [VBORepository](vborepository.md) object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | False |
| Proxy | Specifies a backup proxy server. The cmdlet will move a backup repository or an object storage repository to this backup proxy server. | Accepts the [VBOProxy](vboproxy.md) object.  To get this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | False | Named | False |
| WaitForSessionsTimeoutMinutes | Specifies a timeout in minutes.  The cmdlet will use this timeout to wait for the related sessions to finish before starting the current session. Related sessions are the sessions that Veeam Backup for Microsoft 365 creates to perform different activities: data backup and backup copy, data management, data restore, and data retrieval.  Default: 60 | Int32 | False | Named | False |
| ForceStopSessions | Defines action that Veeam Backup for Microsoft 365 will perform if the related sessions exceed the WaitForSessionsTimeoutMinutes value to finish. The following values are available:   * true - the related sessions are stopped, the change owner session is created and started. * false - the change owner session is canceled.   Default: False | SwitchParameter | False | Named | False |
| ForceStopSessionsTimeoutMinutes | For the ForceStopSessions parameter set to true.  Specifies a timeout in minutes.  The cmdlet will use this timeout to wait for the related sessions to stop after Veeam Backup for Microsoft 365 forced them to stop.  Default: 10 | Int32 | False | Named | False |
| IgnoreConnectionTroublesToSourceLocation | Defines that the cmdlet will ignore the Offline status of a source backup proxy server.  Default: False | SwitchParameter | False | Named | False |
| Force | Defines that the cmdlet will start a session without showing warnings in the PowerShell console.  If you do not provide the parameter, the cmdlet will prompt you to confirm the operation.  Default: False | SwitchParameter | False | Named | False |
| Pool | Specifies a backup proxy pool. The cmdlet will move an object storage repository to this backup proxy pool. | Accepts the [VBOProxyPool](vboproxypool.md) object.  To get this object, run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBORepositoriesOwnerChangeSession](vborepositoriesownerchangesession.md) object that contains details on a session when Veeam Backup for Microsoft 365 moves a backup repository to another backup proxy server or backup proxy pool.

Example

Starting Change Owner Session

This example shows how to start a change owner session to move the Azure Backup object storage repository to the Pool1 backup proxy pool.

|  |
| --- |
| $repository = Get-VBORepository -Name "Azure Backup"  $pool = Get-VBOProxyPool -Name "Pool1"  Start-VBORepositoryOwnerChangeSession -Repository $repository -Pool $pool -ForceStopSessions |

Perform the following steps:

1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable.
2. Run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. Specify the Name parameter value. Save the result to the $pool variable.
3. Run the Start-VBORepositoryOwnerChangeSession cmdlet. Set the $repository variable as the Repository parameter value. Set the $pool variable as the Pool parameter value. Provide the ForceStopSessions parameter.

Related Commands

* [Get-VBORepository](get-vborepository.md)
* [Get-VBOProxyPool](get-vboproxypool.md)
* [Get-VBOProxy](get-vboproxy.md)


