---
title: "get-vbolicense"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbolicense.html"
last_updated: "8/19/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns an installed product license for Veeam Backup for Microsoft 365.

Syntax

|  |
| --- |
| Get-VBOLicense [<CommonParameters>] |

Detailed Description

This cmdlet returns information on the license that is currently installed on the Veeam Backup for Microsoft 365 server. You can get details on the following information: license status, expiration date, license type, contact person name, the number of licensed users, support ID and the support expiration date.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Getting License Installed on Veeam Backup for Microsoft 365

This command returns the license that is currently installed on the Veeam Backup for Microsoft 365 server.

|  |
| --- |
| Get-VBOLicense  Status                : Valid  ExpirationDate        : 4/1/2026 (225 days left)  Type                  : Subscription  Package               : M365Suite  LicensedTo            : Veeam Software GmbH  ContactPerson         :  TotalNumber           : 9999 (2 used)  SupportId             : 12345678  SupportExpirationDate : |

Page updated 8/19/2025

Page content applies to build 8.3.0.2201
