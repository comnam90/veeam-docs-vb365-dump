---
title: "VBOProxy"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboproxy.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOProxy


Contains details about a Veeam Backup for Microsoft 365 backup proxy server.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Backup proxy server ID. |
| Hostname | String | DNS name or IP address of the backup proxy server. |
| Port | Int | Used port number. |
| Description | String | Backup proxy server description. |
| ThreadsNumber | Int | Number of threads that the backup proxy server simultaneously runs to process backup data. |
| ThrottlingValue | Ulong | Threshold for the inbound traffic to the backup proxy server. |
| ThrottlingUnit | VBOThrottlingUnit | Measuring unit for the inbound traffic threshold. Possible values:   * Mbps * MBs * KBs |
| State | VBOProxyState | Backup proxy server state. Possible values:   * Online * Offline |
| ProxyRoles | VBOProxyRoles | Backup proxy server role. Possible values:   * None * Unknown * Scheduler * Orchestrator * Processor * ApplianceProcessor |
| MaintenanceModeState | VBOProxyMaintenanceState | State of the maintenance mode. Possible values:   * Disabled * Enabling * Enabled |
| Type | VBOProxyType | Backup proxy server type. Possible values:   * Local * Domain * Workgroup |
| IsOutdated | Bool | If True, the backup proxy server is marked as Out of Date and must be upgraded. |
| CpuUsagePercent | Double? | CPU usage in percent. |
| MemoryUsagePercent | Double? | Memory usage in percent. |
| OperatingSystemKind | VBOProxyOperatingSystemKind | Operating system type. Possible values:   * Windows * Linux |
| Version | String | Version of Veeam Backup for Microsoft 365 Proxy Service. |
| InternetProxy | [VBOProxyInternetProxySettings](vboproxyinternetproxysettings.md) | Internet proxy server settings. |
| PoolId | GUID | Backup proxy pool ID. |
| ServiceAccount | String | Service account credentials. |
| SshPort | Ushort? | Port number to connect to a Linux-based backup proxy server through SSH.  Default: 22 |
| SshConnectionTimeout | Int? | The SSH connection timeout to wait for connection to a Linux-based backup proxy server through SSH. |

Related Commands

* [Set-VBOConfigurationParameter](set-vboconfigurationparameter.md)
* [Get-VBOProxy](get-vboproxy.md)
* [Add-VBOProxy](add-vboproxy.md)
* [Set-VBOProxy](set-vboproxy.md)
* [Sync-VBOProxy](sync-vboproxy.md)
* [Remove-VBOProxy](remove-vboproxy.md)
* [Update-VBOProxy](update-vboproxy.md)
* [Add-VBOProxyPool](add-vboproxypool.md)
* [Set-VBOProxyPool](set-vboproxypool.md)
* [Set-VBOProxyMaintenance](set-vboproxymaintenance.md)
* [Add-VBORepository](add-vborepository.md)
* [Get-VBORepository](get-vborepository.md)
* [Add-VBOAmazonS3CompatibleRepository](add-vboamazons3compatiblerepository.md)
* [Add-VBOAmazonS3Repository](add-vboamazons3repository.md)
* [Add-VBOAmazonS3GlacierRepository](add-vboamazons3glacierrepository.md)
* [Add-VBOAzureBlobRepository](add-vboazureblobrepository.md)
* [Add-VBOAzureArchiveRepository](add-vboazurearchiverepository.md)
* [Start-VBORepositoryOwnerChangeSession](start-vborepositoryownerchangesession.md)
* [New-VBOAmazonArchiverAppliance](new-vboamazonarchiverappliance.md)
* [New-VBOAzureArchiverAppliance](new-vboazurearchiverappliance.md)


