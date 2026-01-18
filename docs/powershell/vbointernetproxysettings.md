---
title: "VBOInternetProxySettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbointernetproxysettings.html"
last_updated: "1/12/2026"
product_version: "8.3.0.2201"
---

# VBOInternetProxySettings


Contains details about settings of the internet proxy server.

| Property | Type | Description |
| --- | --- | --- |
| UseInternetProxy | Bool | If True, the internet proxy server is used as a gateway. |
| Host | String | DNS name or IP address of the internet proxy server. |
| Port | Int | Used port number. |
| UseAuthentication | Bool | If True, authentication is required to connect to the internet proxy server. |
| User | String | Authentication credentials. |

Related Commands

* [Get-VBOInternetProxySettings](get-vbointernetproxysettings.md)
* [Set-VBOInternetProxySettings](set-vbointernetproxysettings.md)


