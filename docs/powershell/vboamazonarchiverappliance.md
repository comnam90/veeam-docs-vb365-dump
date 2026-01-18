---
title: "VBOAmazonArchiverAppliance"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboamazonarchiverappliance.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBOAmazonArchiverAppliance


Contains details about the Amazon archiver appliance.

| Property | Type | Description |
| --- | --- | --- |
| InstanceType | [VBOAmazonInstanceType](vboamazoninstancetype.md) | Details about an instance type that the archiver appliance uses. |
| VPC | [VBOAmazonVpc](vboamazonvpc.md) | Details about the Amazon Virtual Private Cloud (Amazon VPC). |
| Subnet | [VBOAmazonSubnet](vboamazonsubnet.md) | Details about the archiver appliance subnet. |
| SecurityGroup | [VBOAmazonSecurityGroup](vboamazonsecuritygroup.md) | Details about a security group associated with the archiver appliance. |
| Port | Int | Port number. |
| IpRanges | String[] | Range of IPv4 addresses. |

Related Commands

* [Set-VBOAmazonS3Repository](set-vboamazons3repository.md)
* [Set-VBOAmazonS3GlacierRepository](set-vboamazons3glacierrepository.md)
* [New-VBOAmazonS3ObjectStorageSettings](new-vboamazons3objectstoragesettings.md)
* [Add-VBOAmazonS3ObjectStorageRepository](add-vboamazons3objectstoragerepository.md)
* [Set-VBOObjectStorageRepository](set-vboobjectstoragerepository.md)
* [New-VBOAmazonArchiverAppliance](new-vboamazonarchiverappliance.md)


