---
title: "Get-VBOFederatedAuthenticationAuthority"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbofederatedauthenticationauthority.html"
last_updated: "1/9/2026"
product_version: "8.3.0.2201"
---

# Get-VBOFederatedAuthenticationAuthority


Short Description

Returns external authentication providers.

Syntax

|  |
| --- |
| Get-VBOFederatedAuthenticationAuthority [-Id <Guid>] [<CommonParameters>] |

Detailed Description

This cmdlet returns external authentication providers configured in Veeam Backup for Microsoft 365.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Id | Specifies an ID of the external authentication provider. The cmdlet will return the external authentication provider with this ID. | Guid | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOFederatedAuthenticationAuthority](vbofederatedauthenticationauthority.md) object that contains settings for an external authentication provider.

Example

Getting All External Authentication Providers

This command returns a list of all external authentication providers.

|  |
| --- |
| Get-VBOFederatedAuthenticationAuthority |


