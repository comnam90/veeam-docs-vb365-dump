---
title: "VBOAmazonS3ObjectStorageRepository"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboamazons3objectstoragerepository.html"
last_updated: "1/13/2026"
product_version: "8.3.0.2201"
---

# VBOAmazonS3ObjectStorageRepository


Contains details about Amazon S3 object storage repository or S3 Compatible object storage repository. See also [VBORepository](vborepository.md).

| Property | Type | Description |
| --- | --- | --- |
| Folder | [VBOAmazonS3Folder](vboamazons3folder.md) | Details about an Amazon S3 folder. |
| UseArchiverAppliance | Bool | If True, usage of the Amazon archiver appliance is enabled. |
| ApplianceInfo | [VBOAmazonS3ObjectStorageApplianceInfo](vboamazons3objectstorageapplianceinfo.md) | Details about the Amazon archiver appliance. See also [VBOAmazonArchiverAppliance](vboamazonarchiverappliance.md). |
| ArchiveStorageClass | VBOAmazonS3AwsArchiveStorageClass? | Amazon S3 storage class. Possible values:   * GlacierFlexibleRetrieval * GlacierDeepArchive * GlacierInstantRetrieval |

Related Commands

* [Add-VBOAmazonS3CompatibleRepository](add-vboamazons3compatiblerepository.md)
* [Set-VBOAmazonS3CompatibleRepository](set-vboamazons3compatiblerepository.md)
* [Add-VBOAmazonS3Repository](add-vboamazons3repository.md)
* [Set-VBOAmazonS3Repository](set-vboamazons3repository.md)
* [Add-VBOAmazonS3GlacierRepository](add-vboamazons3glacierrepository.md)
* [Set-VBOAmazonS3GlacierRepository](set-vboamazons3glacierrepository.md)
* [New-VBOAmazonS3CompatibleObjectStorageSettings](new-vboamazons3compatibleobjectstoragesettings.md)
* [New-VBOAmazonS3ObjectStorageSettings](new-vboamazons3objectstoragesettings.md)
* [Add-VBOAmazonS3CompatibleObjectStorageRepository](add-vboamazons3compatibleobjectstoragerepository.md)
* [Add-VBOAmazonS3ObjectStorageRepository](add-vboamazons3objectstoragerepository.md)


