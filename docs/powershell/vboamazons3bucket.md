---
title: "VBOAmazonS3Bucket"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboamazons3bucket.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBOAmazonS3Bucket


Contains details about an Amazon S3 bucket.

| Property | Type | Description |
| --- | --- | --- |
| Name | String | Amazon S3 bucket name. |
| RegionName | String | Amazon S3 region name. |
| RegionId | String | Amazon S3 region ID. For example, us-east-1. |
| ConnectionSettings | [VBOS3ConnectionSettings](vbos3connectionsettings.md) | Connection settings to Amazon S3 object storage repository or S3 Compatible object storage repository. See also [VBOAmazonS3ConnectionSettings](vboamazons3connectionsettings.md) and [VBOAmazonS3CompatibleConnectionSettings](vboamazons3compatibleconnectionsettings.md). |

Related Commands

* [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md)
* [Add-VBOAmazonS3Folder](add-vboamazons3folder.md)
* [Get-VBOAmazonS3Folder](get-vboamazons3folder.md)


