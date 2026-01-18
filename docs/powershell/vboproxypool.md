---
title: "VBOProxyPool"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboproxypool.html"
last_updated: "12/8/2025"
product_version: "8.3.0.2201"
---

# VBOProxyPool


Contains details about a backup proxy pool.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Backup proxy pool ID. |
| Name | String | Backup proxy pool name. |
| Description | String | Backup proxy pool description. |
| Proxies | [VBOProxy](vboproxy.md)[] | Array of backup proxy servers. |

Related Commands

* [Set-VBOConfigurationParameter](set-vboconfigurationparameter.md)
* [Get-VBOProxyPool](get-vboproxypool.md)
* [Add-VBOProxyPool](add-vboproxypool.md)
* [Set-VBOProxyPool](set-vboproxypool.md)
* [Remove-VBOProxyPool](remove-vboproxypool.md)

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


