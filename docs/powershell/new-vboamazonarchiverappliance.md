---
title: "new-vboamazonarchiverappliance"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vboamazonarchiverappliance.html"
last_updated: "8/19/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Defines the Amazon archiver appliance settings.

Syntax

This cmdlet provides parameter sets that allow you to:

* Define the Amazon archiver appliance settings by specifying a range of IPv4 addresses for a security group.

|  |
| --- |
| New-VBOAmazonArchiverAppliance [-InstanceType <VBOAmazonInstanceType>] [-Port <Int32>] [-VPC <VBOAmazonVpc>] [-Subnet <VBOAmazonSubnet>] [-SecurityGroup <VBOAmazonSecurityGroup>] -IpRanges <String[]> [<CommonParameters>] |

* Define the Amazon archiver appliance settings by specifying a public IPv4 address of a backup proxy server.

|  |
| --- |
| New-VBOAmazonArchiverAppliance [-InstanceType <VBOAmazonInstanceType>] [-Port <Int32>] [-VPC <VBOAmazonVpc>] [-Subnet <VBOAmazonSubnet>] [-SecurityGroup <VBOAmazonSecurityGroup>] -ProxyIpRange <VBOProxy> [<CommonParameters>] |

* Define the Amazon archiver appliance settings by specifying public IPv4 addresses of all backup proxy servers added to a backup proxy pool.

|  |
| --- |
| New-VBOAmazonArchiverAppliance [-InstanceType <VBOAmazonInstanceType>] [-Port <Int32>] [-VPC <VBOAmazonVpc>] [-Subnet <VBOAmazonSubnet>] [-SecurityGroup <VBOAmazonSecurityGroup>] -ProxyPoolIpRange <VBOProxyPool> [<CommonParameters>] |

Detailed Description

This cmdlet creates the VBOAmazonArchiverAppliance object. This object contains settings of the Amazon archiver appliance that Veeam Backup for Microsoft 365 will use when transferring backed-up data between different instances of the general purpose object storage repositories (Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes) or to any of Amazon S3 Glacier object storage repositories (Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes).

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| InstanceType | Specifies an instance type that the archiver appliance will use.  For more information on instance types, see [this Amazon article](https://aws.amazon.com/ec2/instance-types/).  Default: m6i.xlarge (4 CPU/16 GB) | Accepts the VBOAmazonInstanceType object.  To get this object, run the [Get-VBOAmazonInstanceType](get-vboamazoninstancetype.md) cmdlet. | False | Named | False |
| Port | Specifies a port number. The cmdlet will use this port number to route requests between the archiver appliance and Veeam Backup for Microsoft 365 backup infrastructure components.  Default: 443 | Int32 | False | Named | False |
| VPC | Specifies the Amazon Virtual Private Cloud (Amazon VPC). The cmdlet will launch the target EC2 instance on this Amazon VPC.  For more information on the Amazon VPC, see [this Amazon article](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html).  Default: Create new  This value indicates that a new Amazon VPC will be created in a region where a bucket with the specified folder is located when you run the [Add-VBOAmazonS3ObjectStorageRepository](add-vboamazons3objectstoragerepository.md) or [Add-VBOAmazonS3GlacierRepository](add-vboamazons3glacierrepository.md) or [Add-VBOAmazonS3Repository](add-vboamazons3repository.md) cmdlet. | Accepts the VBOAmazonVpc object.  To get this object, run the [Get-VBOAmazonVPC](get-vboamazonvpc.md) cmdlet. | False | Named | False |
| Subnet | Specifies the archiver appliance subnet.  Default: Create new  This value indicates that a new subnet will be created in a region where a bucket with the specified folder is located when you run the [Add-VBOAmazonS3ObjectStorageRepository](add-vboamazons3objectstoragerepository.md) or [Add-VBOAmazonS3GlacierRepository](add-vboamazons3glacierrepository.md) or [Add-VBOAmazonS3Repository](add-vboamazons3repository.md) cmdlet. | Accepts the VBOAmazonSubnet object.  To get this object, run the [Get-VBOAmazonSubnet](get-vboamazonsubnet.md) cmdlet. | False | Named | False |
| SecurityGroup | Specifies a security group that will be associated with the archiver appliance.  For more information on security groups for Amazon VPC, see [this Amazon article](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html).  Default: Create new  This value indicates that a new security group will be created in a region where a bucket with the specified folder is located when you run the [Add-VBOAmazonS3ObjectStorageRepository](add-vboamazons3objectstoragerepository.md) or [Add-VBOAmazonS3GlacierRepository](add-vboamazons3glacierrepository.md) or [Add-VBOAmazonS3Repository](add-vboamazons3repository.md) cmdlet. | Accepts the VBOAmazonSecurityGroup object.  To get this object, run the [Get-VBOAmazonSecurityGroup](get-vboamazonsecuritygroup.md) cmdlet. | False | Named | False |
| IpRanges | Specifies a range of IPv4 addresses for the specified security group. | String[] | True | Named | False |
| ProxyIpRange | Specifies public IPv4 address of a backup proxy server. | Accepts the VBOProxy object.  To get this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | True | Named | False |
| ProxyPoolIpRange | Specifies public IPv4 addresses of all backup proxy servers added to a backup proxy pool. | Accepts the VBOProxyPool object.  To get this object, run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonArchiverAppliance object that contains the Amazon archiver appliance settings.

Example

Creating Amazon Archiver Appliance

This example shows how to define the Amazon archiver appliance settings.

|  |
| --- |
| $S3account = Get-VBOAmazonS3Account -AccessKey "?Iqws8NewidZydk"  $S3connection = New-VBOAmazonS3ConnectionSettings -Account $S3account -RegionType Global  $inst = Get-VBOAmazonInstanceType -AmazonS3ConnectionSettings $S3connection -RegionId eu-central-1 -Name m6i.2xlarge  $VPC = Get-VBOAmazonVPC -AmazonS3ConnectionSettings $S3connection -RegionId eu-central-1 -Name "VPCName"  $subnet = Get-VBOAmazonSubnet -VPC $VPC -Name "SubnetName"  $sgroup = Get-VBOAmazonSecurityGroup -VPC $VPC -Name "SecurityGroupName"  New-VBOAmazonArchiverAppliance -InstanceType $inst -VPC $VPC -Subnet $subnet -SecurityGroup $sgroup -IpRanges @("217.113.11.0/24","124.31.42.18") -Port 80 |

Perform the following steps:

1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the AccessKey parameter value. Save the result to the $S3account variable.
2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Set the $S3account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $S3connection variable.
3. Run the [Get-VBOAmazonInstanceType](get-vboamazoninstancetype.md) cmdlet. Set the $S3connection variable as the AmazonS3ConnectionSettings parameter value. Specify the RegionId parameter value. Specify the Name parameter value. Save the result to the $inst variable.
4. Run the [Get-VBOAmazonVPC](get-vboamazonvpc.md) cmdlet. Set the $S3connection variable as the AmazonS3ConnectionSettings parameter value. Specify the RegionId parameter value. Specify the Name parameter value. Save the result to the $VPC variable.
5. Run the [Get-VBOAmazonSubnet](get-vboamazonsubnet.md) cmdlet. Set the $VPC variable as the VPC parameter value. Specify the Name parameter value. Save the result to the $subnet variable.
6. Run the [Get-VBOAmazonSecurityGroup](get-vboamazonsecuritygroup.md) cmdlet. Set the $VPC variable as the VPC parameter value. Specify the Name parameter value. Save the result to the $sgroup variable.
7. Run the New-VBOAmazonArchiverAppliance cmdlet. Specify the following settings:

* Set the $inst variable as the InstanceType parameter value.
* Set the $VPC variable as the VPC parameter value.
* Set the $subnet variable as the Subnet parameter value.
* Set the $sgroup variable as the SecurityGroup parameter value.

* Specify the IpRanges parameter value.

* Specify the Port parameter value.

Related Commands

* [Get-VBOAmazonInstanceType](get-vboamazoninstancetype.md)
* [Get-VBOAmazonSecurityGroup](get-vboamazonsecuritygroup.md)
* [Get-VBOAmazonSubnet](get-vboamazonsubnet.md)
* [Get-VBOAmazonVPC](get-vboamazonvpc.md)
* [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md)
* [Get-VBOAmazonS3Account](get-vboamazons3account.md)

* [Get-VBOProxy](get-vboproxy.md)
* [Get-VBOProxyPool](get-vboproxypool.md)

Page updated 8/19/2024

Page content applies to build 8.3.0.2201
