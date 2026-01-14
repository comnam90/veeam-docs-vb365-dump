---
title: "new-vboamazons3connectionsettings"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vboamazons3connectionsettings.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Defines connection settings to Amazon S3 object storage repository.

Syntax

|  |
| --- |
| New-VBOAmazonS3ConnectionSettings -Account <VBOAmazonS3Account> -RegionType <VBOAmazonS3RegionType> [<CommonParameters>] |

Detailed Description

This cmdlet creates the VBOAmazonS3ConnectionSettings object. This object contains connection settings to Amazon S3 object storage repository.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Account | Specifies Amazon S3 storage account credentials. The cmdlet will use these storage account credentials to connect to Amazon S3 object storage repository. | Accepts the VBOAmazonS3Account object.  To get this object, run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. | True | Named | False |
| RegionType | Specifies the region type for Amazon S3 object storage repository. The cmdlet will connect to the selected region type and will set up a connection with Amazon S3 object storage repository. You can select the following region type:   * Global * USGovernment * China | VBOAmazonS3RegionType | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3ConnectionSettings object that defines connection settings to Amazon S3 object storage repository.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Connecting to Amazon S3 Object Storage of Global Region Type

|  |  |
| --- | --- |
| This example shows how to connect to Amazon S3 object storage repository of the Global region type.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id 26e61916-0257-4a05-8f65-204628d2ed7a  New-VBOAmazonS3ConnectionSettings -Account $account -RegionType Global |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the New-VBOAmazonS3ConnectionSettings cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Connecting to Amazon S3 Object Storage of US Government Region Type

|  |  |
| --- | --- |
| This example shows how to connect to Amazon S3 object storage repository of the US Government region type.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id d1fc1171-3206-429f-9563-51b9af8df0ac  New-VBOAmazonS3ConnectionSettings -Account $account -RegionType USGovernment |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the New-VBOAmazonS3ConnectionSettings cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Connecting to Amazon S3 Object Storage of China Region Type

|  |  |
| --- | --- |
| This example shows how to connect to Amazon S3 object storage repository of the China region type.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id f7e0a65d-1042-4ab0-bc73-699acbb5cb79  New-VBOAmazonS3ConnectionSettings -Account $account -RegionType China |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the New-VBOAmazonS3ConnectionSettings cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. |

Related Commands

[Get-VBOAmazonS3Account](get-vboamazons3account.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
