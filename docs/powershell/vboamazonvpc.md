---
title: "VBOAmazonVpc"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboamazonvpc.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBOAmazonVpc


Contains details about the Amazon Virtual Private Cloud (Amazon VPC).

| Property | Type | Description |
| --- | --- | --- |
| Id | String | Amazon Virtual Private Cloud ID. |
| Name | String | Amazon Virtual Private Cloud name. |
| CIDR | String | Range of IPv4 addresses for the Amazon Virtual Private Cloud in the form of a Classless Inter-Domain Routing (CIDR) block. |
| RegionId | String | Amazon S3 region ID. For example, us-east-1. |
| ConnectionSettings | [VBOAmazonS3ConnectionSettings](vboamazons3connectionsettings.md) | Details about connection settings to Amazon S3 object storage repository. |

Related Commands

* [New-VBOAmazonArchiverAppliance](new-vboamazonarchiverappliance.md)
* [Get-VBOAmazonSecurityGroup](get-vboamazonsecuritygroup.md)
* [Get-VBOAmazonSubnet](get-vboamazonsubnet.md)
* [Get-VBOAmazonVPC](get-vboamazonvpc.md)


