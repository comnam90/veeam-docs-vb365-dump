---
title: "add-vbofederatedauthenticationauthority"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vbofederatedauthenticationauthority.html"
last_updated: "2/27/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Adds an external authentication provider.

Syntax

|  |
| --- |
| Add-VBOFederatedAuthenticationAuthority -Name <String> [-Description <String>] -Issuer <String> -PublicCertificate <String> [<CommonParameters>] |

Detailed Description

This cmdlet adds an external authentication provider.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Name | Specifies a name of the external authentication provider. The cmdlet will add an external authentication provider with this name. | String | True | Named | False |
| Description | Specifies a description of the external authentication provider. The cmdlet will add an external authentication provider with this description. | String | False | Named | False |
| Issuer | Specifies the authorization token issuer. | String | True | Named | False |
| PublicCertificate | Specifies the public part of the certificate provided as a Base64 string. The private part of this certificate is used for signing authorization tokens. | String | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOFederatedAuthenticationAuthority object that contains settings for an external authentication provider.

Example

Adding External Authentication Provider

This command adds an external authentication provider.

|  |
| --- |
| Add-VBOFederatedAuthenticationAuthority -Name "External\_Provider" -Issuer "Issuer" -PublicCertificate "MIIC/DCCAeSgAwIBAgIQZGLYVWufprVLgQgAUWK7UjANBgkqhkiG9w0BAQsFADAQMQ4wDAYDVQQDDAVjZXJ0eDAgFw0yNDA1MTAwOTIyNTBaGA8yMTIzMDUxMDA5MzI0NFowEDEOMAwGA1UEAwwFY2VydHgwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDj53Pp419Q7QiunfNoMB4bLrA8Sv4+neorf2a4+zwc9tufTUOe9OpoNXy/7Jck+XS3R4jx8jDsSTmEwShTFKZZ+Q0KdiiV61TRa+rdv1kVzxa9892bahcbTj3DEw7K/+ozuw+HDTXlP1E7rmxzFunFArm1ucQjbDDVD+JQl37MjiXrnexrx54IeaPy0PZk8FGNmXCBSzWLFDaRB7p8JOYsfgkSiDLQklrYGUQA6S5QSYRQNSN7PHb6hDwKqKoXABspciRmex1MTgvNV3i06ZznfDQ+FlBKxRhJK5JSagjfoZmleZAY/YCMY+mooDAPzqkVTGOvAMta1yB7PmaGVs29AgMBAAGjUDBOMA4GA1UdDwEB/wQEAwIFoDAdBgNVHSUEFjAUBggrBgEFBQcDAgYIKwYBBQUHAwEwHQYDVR0OBBYEFPQMkL0XY0ey6prJktPeUxphwcZOMA0GCSqGSIb3DQEBCwUAA4IBAQDOcnU9ao5cIaaSF1mG40zy70WVsJtbsydtqnShy7XGj+KPwXQp5JXCL5THduqUnv787SQmJf6n+9ryqjRXjCUpJf0ukuLUKOOrtzsncbG6pp1d/VkM9GOTtX9aAy6ejqa+KJYM1mfqUXaSElW1H99gIHpJAfoXMKjqSv854X1LXuaYxcVKAsab+WILZn+qyFvtkQqFqZtuQcdbLq+D9K59QCkRwOd44nfJ0ZYF4K0npgw/3egGYUYUEnyvT+gBpjfZsyntup1JvHcpN84od/rXj01CUjT6GZXtJcLflo8k1cw87Ck9RNly4GNFPeM8z0Xq8QRDRBj/X48YSEZtGc3h" |

Page updated 2/27/2025

Page content applies to build 8.3.0.2201
