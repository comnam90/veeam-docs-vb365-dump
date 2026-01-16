---
title: "vbo_proxy_server_address_linux"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_proxy_server_address_linux.html"
last_updated: "8/28/2024"
product_version: "8.3.0.2201"
---


In this article

At this step of the wizard, specify a computer that you want to use as a backup proxy server, its port number and optional description.

|  |
| --- |
| Note |
| Veeam Backup for Microsoft 365 requires the Veeam Backup for Microsoft 365 server and a backup proxy server to be reachable to each other by their DNS name. |

Do the following:

1. In the Host field, enter a DNS name or IP address of a computer that you want to use as a backup proxy server.

If the specified computer does not have a direct access to the internet, you can [configure an internet proxy server](vbo_internet_proxy.md) for such a computer.

1. In the Port field, enter a port number to access the specified computer.
2. In the Description field, enter optional description.

[![Adding Backup Proxy Server](images/add_proxy_name_linux.webp)](images/add_proxy_name_linux.webp "Adding Backup Proxy Server")

Page updated 8/28/2024

Page content applies to build 8.3.0.2201
