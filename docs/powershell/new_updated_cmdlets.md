---
title: "new_updated_cmdlets"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new_updated_cmdlets.html"
last_updated: "5/27/2025"
product_version: "8.3.0.2201"
---


In this article

This section contains information on new and updated PowerShell cmdlets in Veeam Backup for Microsoft 365 8.

New Cmdlets

| Cmdlet | Operation |
| --- | --- |
| [Set-VBOConfigurationParameter](set-vboconfigurationparameter.md) | Modifies configuration of the Veeam Backup for Microsoft 365 controller, backup proxy servers and backup proxy pools. |
| [Set-VBOPSQLDatabaseServerLimits](set-vbopsqldatabaseserverlimits.md) | Modifies settings of the PostgreSQL instance. |
| [New-VBOLinuxCredential](new-vbolinuxcredential.md) | Creates the Linux credentials record to connect to a Linux-based backup proxy server. |
| [Get-VBOProxyPool](get-vboproxypool.md) | Returns backup proxy pools added to the Veeam Backup for Microsoft 365 infrastructure. |
| [Add-VBOProxyPool](add-vboproxypool.md) | Adds backup proxy pools. |
| [Set-VBOProxyPool](set-vboproxypool.md) | Modifies settings of backup proxy pools. |
| [Remove-VBOProxyPool](remove-vboproxypool.md) | Removes backup proxy pools. |
| [Set-VBOProxyMaintenance](set-vboproxymaintenance.md) | Enables or disables maintenance mode for backup proxy servers that are already added to a backup proxy pool. |
| [Add-VBOAmazonS3CompatibleRepository](add-vboamazons3compatiblerepository.md) | Adds S3 Compatible object storage repository. |
| [Set-VBOAmazonS3CompatibleRepository](set-vboamazons3compatiblerepository.md) | Modifies settings of S3 Compatible object storage repository. |
| [Add-VBOAmazonS3Repository](add-vboamazons3repository.md) | Adds Amazon S3 object storage repository (Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes). |
| [Set-VBOAmazonS3Repository](set-vboamazons3repository.md) | Modifies settings of Amazon S3 object storage repository (Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes). |
| [Add-VBOAmazonS3GlacierRepository](add-vboamazons3glacierrepository.md) | Adds Amazon S3 object storage repository (Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes). |
| [Set-VBOAmazonS3GlacierRepository](set-vboamazons3glacierrepository.md) | Modifies settings of Amazon S3 object storage repository (Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes). |
| [Add-VBOAzureBlobRepository](add-vboazureblobrepository.md) | Adds Azure Blob Storage. |
| [Set-VBOAzureBlobRepository](set-vboazureblobrepository.md) | Modifies settings of Azure Blob Storage. |
| [Add-VBOAzureArchiveRepository](add-vboazurearchiverepository.md) | Adds Azure Blob Storage Archive. |
| [Set-VBOAzureArchiveRepository](set-vboazurearchiverepository.md) | Modifies settings of Azure Blob Storage Archive. |
| [New-VBOAmazonS3CompatibleObjectStorageSettings](new-vboamazons3compatibleobjectstoragesettings.md) | Defines the S3 Compatible object storage repository settings. |
| [New-VBOAmazonS3ObjectStorageSettings](new-vboamazons3objectstoragesettings.md) | Defines the Amazon S3 object storage repository settings. |
| [New-VBOAzureBlobObjectStorageSettings](new-vboazureblobobjectstoragesettings.md) | Defines the Azure Blob Storage settings. |
| [Start-VBORepositoryOwnerChangeSession](start-vborepositoryownerchangesession.md) | Creates and starts a change owner session to move a backup repository to another backup proxy server or backup proxy pool. |
| [Get-VBORepositoryOwnerChangeSession](get-vborepositoryownerchangesession.md) | Returns a change owner session started to move a backup repository to another backup proxy server or backup proxy pool. |
| [Stop-VBORepositoryOwnerChangeSession](stop-vborepositoryownerchangesession.md) | Stops change owner sessions. |
| [Add-VBOFederatedAuthenticationAuthority](add-vbofederatedauthenticationauthority.md) | Adds external authentication providers. |
| [Get-VBOFederatedAuthenticationAuthority](get-vbofederatedauthenticationauthority.md) | Returns external authentication providers. |
| [Remove-VBOFederatedAuthenticationAuthority](remove-vbofederatedauthenticationauthority.md) | Removes external authentication providers. |
| [Start-VBORepositoryIndexingSession](start-vborepositoryindexingsession.md) | Creates and starts an indexing session when a backup proxy server collects and sends the restore points metadata of a backup repository associated with this backup proxy server to the Veeam Backup for Microsoft 365 controller. |

Updated Cmdlets

| Cmdlet | Operation |
| --- | --- |
| [Set-VBOServerComponents](set-vboservercomponents.md) | Parameter added: EnableDistributedTracing |
| [Get-VBOProxy](get-vboproxy.md) | Parameter deprecated: ExtendedView |
| [Add-VBOProxy](add-vboproxy.md) | Parameters deprecated: Credential, ThreadsNumber  Parameters added: WindowsCredential, LinuxCredential, CreateServiceAccount |
| [Set-VBOProxy](set-vboproxy.md) | Parameter deprecated: Credential, ThreadsNumber  Parameters added: WindowsCredential, LinuxCredential |
| [Remove-VBOProxy](remove-vboproxy.md) | Parameter deprecated: Credential  Parameters added: WindowsCredential, LinuxCredential |
| [Update-VBOProxy](update-vboproxy.md) | Parameter deprecated: Credential  Parameters added: WindowsCredential, LinuxCredential |
| [Add-VBORepository](add-vborepository.md) | Parameters added: ProxyPool, IgnoreProxyPoolApplianceAccessValidation |
| [Get-VBORepository](get-vborepository.md) | Parameter added: ProxyPool |
| [Remove-VBORepository](remove-vborepository.md) | Parameter added: Force |
| [Add-VBOAmazonS3CompatibleObjectStorageRepository](add-vboamazons3compatibleobjectstoragerepository.md) | Parameter added: ImmutabilityPeriodDays |
| [Add-VBOAmazonS3ObjectStorageRepository](add-vboamazons3objectstoragerepository.md) | Parameter added: ImmutabilityPeriodDays |
| [Add-VBOAzureBlobObjectStorageRepository](add-vboazureblobobjectstoragerepository.md) | Parameter added: ImmutabilityPeriodDays |
| [Set-VBOObjectStorageRepository](set-vboobjectstoragerepository.md) | Parameter added: IgnoreProxyPoolApplianceAccessValidation |
| [New-VBOAmazonArchiverAppliance](new-vboamazonarchiverappliance.md) | Parameters added: IpRanges, ProxyIpRange, ProxyPoolIpRange |
| [New-VBOAzureArchiverAppliance](new-vboazurearchiverappliance.md) | Parameters added: IpRanges, ProxyIpRange, ProxyPoolIpRange |
| [New-VBOOffice365ConnectionSettings](new-vbooffice365connectionsettings.md) | Parameter deprecated: Credential |
| [Set-VBOOffice365ConnectionSettings](set-vbooffice365connectionsettings.md) | Parameter deprecated: Credential |
| [Set-VBORestAPISettings](set-vborestapisettings.md) | Parameters added: EnableSwaggerUI, EnableOperatorAuthenticationOnly |
| [Get-VBOOrganizationGroup](get-vboorganizationgroup.md) | Parameter deprecated: Name |
| [Get-VBOOrganizationUser](get-vboorganizationuser.md) | Parameter deprecated: Name |

Page updated 5/27/2025

Page content applies to build 8.3.0.2201
