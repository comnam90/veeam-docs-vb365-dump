---
title: "remove-vbofederatedauthenticationauthority"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vbofederatedauthenticationauthority.html"
last_updated: "5/30/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Removes external authentication providers.

Syntax

|  |
| --- |
| Remove-VBOFederatedAuthenticationAuthority -Authority <VBOFederatedAuthenticationAuthority> [<CommonParameters>] |

Detailed Description

This cmdlet removes an external authentication provider.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Authority | Specifies an external authentication provider. The cmdlet will remove this external authentication provider. | Accepts the VBOFederatedAuthenticationAuthority object.  To get this object, run the [Get-VBOFederatedAuthenticationAuthority](get-vbofederatedauthenticationauthority.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing External Authentication Provider

This example shows how to remove an external authentication provider.

|  |
| --- |
| $authority = Get-VBOFederatedAuthenticationAuthority -Id 8657138e-ca49-4f91-XXXX-a17818eb818e  Remove-VBOFederatedAuthenticationAuthority -Authority $authority |

Perform the following steps:

1. Run the [Get-VBOFederatedAuthenticationAuthority](get-vbofederatedauthenticationauthority.md) cmdlet. Specify the Id parameter value. Save the result to the $authority variable.
2. Run the Remove-VBOFederatedAuthenticationAuthority cmdlet. Set the $authority variable as the Authority parameter value.

Related Commands

[Get-VBOFederatedAuthenticationAuthority](get-vbofederatedauthenticationauthority.md)

Page updated 5/30/2024

Page content applies to build 8.3.0.2201
