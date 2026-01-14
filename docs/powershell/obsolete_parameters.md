---
title: "obsolete_parameters"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/obsolete_parameters.html"
last_updated: "11/10/2025"
product_version: "8.3.0.2201"
---


In this article

The following parameters are obsolete and they are no longer working in PowerShell for Veeam Backup for Microsoft 365 version 8.3. If you have used them in your scripts before, make sure that you have updated these scripts.

| Cmdlet | Parameters |
| --- | --- |
| Sync-VBOEntity | all parameters |
| Set-VBOEncryptionKey | all parameters |
| Measure-VBOOrganizationFullBackupSize | all parameters |
| [Add-VBOOrganization](add-vboorganization.md) | * ExchangeConfigureThrottlingPolicy * ExchangeOnPremisesCredential * ExchangeOnPremisesGrantImpersonation * ExchangeServerName * ExchangeSkipCAVerification * ExchangeSkipCommonNameVerification * ExchangeSkipRevocationCheck * ExchangeUseSSL * Office365Credential * Office365GrantAccessToSiteCollections * Office365GrantImpersonation * Office365Region * Office365UseVeeamAADApplication * SharePointCredential * SharePointGrantAccessToSiteCollections * SharePointServerName * SharePointServerPort * SharePointSkipCAVerification * SharePointSkipCommonNameVerification * SharePointSkipRevocationCheck * SharePointUseSSL * Type |
| [Set-VBOOrganization](set-vboorganization.md) | * ExchangeConfigureThrottlingPolicy * ExchangeOnPremisesCredential * ExchangeOnPremisesGrantImpersonation * ExchangeServerName * ExchangeSkipCAVerification * ExchangeSkipCommonNameVerification * ExchangeSkipRevocationCheck * ExchangeUseSSL * IsExchange * IsSharePoint * Office365Credential * Office365GrantAccessToSiteCollections * Office365GrantImpersonation * Office365Region * Office365UseVeeamAADApplication * SharePointCredential * SharePointGrantAccessToSiteCollections * SharePointServerName * SharePointServerPort * SharePointSkipCAVerification * SharePointSkipCommonNameVerification * SharePointSkipRevocationCheck * SharePointUseSSL * Type |
| [Set-VBOProxy](set-vboproxy.md) | EnableTeamsGraphAPIBackup |
| [Set-VBORepository](set-vborepository.md) | Defragmentation |
| [Set-VBOServer](set-vboserver.md) | EnableTeamsGraphAPIBackup |

Page updated 11/10/2025

Page content applies to build 8.3.0.2201
