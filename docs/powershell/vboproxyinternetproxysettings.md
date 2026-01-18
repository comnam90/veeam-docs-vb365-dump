---
title: "VBOProxyInternetProxySettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboproxyinternetproxysettings.html"
last_updated: "1/9/2026"
product_version: "8.3.0.2201"
---

# VBOProxyInternetProxySettings


Contains details about settings of the internet proxy server. See also [VBOProxy](vboproxy.md).

| Property | Type | Description |
| --- | --- | --- |
| UseInternetProxy | Bool | If True, the internet proxy server is used as a gateway. |
| Host | String | DNS name or IP address of the internet proxy server. |
| Port | Int | Used port number. |
| UseAuthentication | Bool | If True, authentication is required to connect to the internet proxy server. |
| User | String | Authentication credentials. |
| UseManagementServerSettings | Bool | If True, the backup server settings are used. |


